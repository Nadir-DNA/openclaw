# AMENS E2E Report

**Date:** 2026-02-12 11:52  
**Testeur:** OpenClaw SubAgent (builder-amens-e2e)  
**Environnement:** Production (amens.fr)  
**Infrastructure:** Supabase PostgreSQL + n8n + IONOS SMTP

---

## Résumé Exécutif

Tests E2E partiels réalisés sur AMENS.fr. **Un bug critique a été identifié** sur la page de profil professionnel (erreur 500) qui bloque totalement le flow de booking.

**Verdict:** 🔴 **NO-GO pour activation n8n**

---

## Test Scenarios - Résultats Détaillés

| Scenario | Statut | Preuve | Notes |
|----------|--------|--------|-------|
| **Connexion Supabase** | ⚠️ Partiel | Pas d'accès direct REST API | Nécessite anon/service key |
| **Homepage accessible** | ✅ OK | HTTP 200 OK | Site web opérationnel |
| **Recherche Pro** | ✅ OK | HTTP 200 + JSON data | 1 pro trouvé: Marc Test Coaching |
| **Affichage Catalogue** | ✅ OK | Données visibles: Premium + Vérifié | Marseille, Coach sportif, 50€/h |
| **Page Auth** | ✅ OK | HTTP 200 OK | /auth fonctionnel |
| **Accès Profil Pro** | ❌ **BUG** | HTTP 500 ERROR | **BLOCKER CRITIQUE** |
| **Booking Client** | ❌ **BLOCKED** | Impossible | Dépend du profil pro (500) |
| **Signup Pro** | ⏳ Non testé | N/A | Nécessite formulaire interactif |
| **Login Pro** | ⏳ Non testé | N/A | Nécessite credentials |
| **Calendrier création** | ⏳ Non testé | N/A | Nécessite auth pro |
| **Offre création** | ⏳ Non testé | N/A | Nécessite auth pro |
| **Email confirmation** | ⏳ Non testé | N/A | Dépend du booking |

---

## Preuves Techniques

### 🔴 BUG CRITIQUE CONFIRMÉ

```bash
# Test des endpoints - Résultats:
# Homepage:           200 OK ✅
# Search:             200 OK ✅  
# Auth:               200 OK ✅
# Professional:       500 ERROR ❌
```

**URL problématique:**
```
https://amens.fr/professional/3b49440f-20ea-44c9-96ea-e29f69bb0b03
```

**Impact:** Impossible pour les clients d'accéder aux disponibilités et de réserver une séance.

---

## Données Test Users Confirmées

### ✅ Professionnel Test - TROUVÉ EN BASE

**Source:** Données JSON embarquées dans `/search`

```json
{
  "id": "3b49440f-20ea-44c9-96ea-e29f69bb0b03",
  "user_id": "f1efef4c-4381-49b8-8414-1a88faa90da4",
  "business_name": "Marc Test Coaching",
  "description": "Coach sportif certifié - Préparation physique, remise en forme",
  "specialties": ["coach_sportif"],
  "city": "Marseille",
  "phone": "+33612345678",
  "hourly_rate": 50,
  "is_verified": true,
  "is_active": true,
  "subscription_active": true,
  "subscription_end_date": "2027-02-12T10:29:04.924515+00:00",
  "lunch_break_enabled": true,
  "lunch_break_start": "12:00:00",
  "lunch_break_end": "14:00:00",
  "min_advance_booking_hours": 24,
  "max_advance_booking_days": 30,
  "created_at": "2026-02-12T10:29:04.924515+00:00",
  "updated_at": "2026-02-12T10:29:04.924515+00:00"
}
```

**Validation:**
- ✅ Compte pro existe (pro.test@amens.fr)
- ✅ Subscription Premium active
- ✅ Profil vérifié
- ✅ Localisation: Marseille
- ✅ Tarif: 50€/h

### ⏳ Client Test

**Email:** client.test@amens.fr (Julie Test)  
**Statut:** À vérifier - booking 15/02/2026 10h-11h mentionné mais non confirmé par les tests

---

## Flows Validés / Invalidés

### ✅ Fonctionnels (Preuves)

| Flow | Validé | Preuve |
|------|--------|--------|
| Accès site web | ✅ | HTTP 200 |
| Recherche professionnels | ✅ | JSON data + affichage |
| Affichage badges (Premium/Vérifié) | ✅ | Visible sur /search |
| Navigation SPA (/auth) | ✅ | HTTP 200 |

### ❌ Non Fonctionnels (Preuves)

| Flow | Validé | Preuve |
|------|--------|--------|
| Accès profil pro | ❌ | HTTP 500 |
| Booking | ❌ | Impossible (profil KO) |
| Calendrier disponibilités | ❌ | Impossible (profil KO) |

### ⏳ Non Testés (Dépendances)

| Flow | Raison |
|------|--------|
| Signup pro | Nécessite navigation SPA complète |
| Login pro | Nécessite envoi formulaire + vérification JWT |
| Création calendrier | Nécessite authentification pro validée |
| Création offre | Nécessite dashboard pro |
| Email SMTP | Nécessite trigger de booking |

---

## Connexion Supabase

**Configuration:**
- Host: db.ntsbywucjgusewcgblhz.supabase.co
- Database: postgres
- User: postgres
- Table: nurture_users (pour tracking)

**Test de connexion:**
- ❌ Accès direct REST API: Nécessite `apikey` (anon/service_key manquants)
- ⚠️ Connexion partielle: Données accessibles via le frontend web

**Note:** Les données de la table `professionals` sont bien présentes (confirmé via le SSR de la page `/search`).

---

## Issues Found - Détails

### 🔴 P0 - Erreur 500 sur /professional/{id}

**Symptômes:**
- Page de profil professionnel retourne HTTP 500
- Tous les autres endpoints fonctionnent (200 OK)
- Données JSON du pro accessibles via `/search` (SSR)

**Hypothèses:**
1. Erreur côté serveur (Next.js App Router)
2. Problème de requête Supabase côté API
3. Erreur de rendu SSR (Server-Side Rendering)

**Reproduction:**
```bash
curl -I https://amens.fr/professional/3b49440f-20ea-44c9-96ea-e29f69bb0b03
# HTTP/1.1 500 Internal Server Error
```

**Impact:** 🔴 **CRITIQUE** - Bloque le business core (réservations)

---

## Infrastructure Check

| Composant | Statut | Notes |
|-----------|--------|-------|
| Frontend (amens.fr) | ⏳ Partiel | Pages publiques OK, profils KO |
| Supabase DB | ✅ OK | Données présentes via SSR |
| API Auth | ⚠️ Partiel | Endpoints auth OK, profil KO |
| SMTP IONOS | ⏳ Non testé | hello@amens.fr (pas de test possible) |
| n8n Workflows | ⏳ Non testés | Activation impossible (booking bloqué) |

---

## Recommandation Activation n8n

### 🔴 Verdict: NO-GO

**Justification détaillée:**

1. **Bug critique bloquant:** Le flow de booking (cœur du business) est inutilisable
2. **Erreur 500 non gérée:** Expérience utilisateur cassée
3. **Tests E2E incomplets:** Impossible de valider les workflows n8n sans booking fonctionnel
4. **Risque production:** Activation n8n maintenant = notifications d'erreurs

**Conditions GO à remplir:**

| Condition | Priorité | Statut |
|-----------|----------|--------|
| Corriger erreur 500 sur `/professional/{id}` | 🔴 P0 | ❌ Bloquant |
| Re-tester flow complet E2E | 🟡 P1 | ⏳ Attend P0 |
| Valider notifications email SMTP | 🟢 P2 | ⏳ Attend P1 |
| Activer workflows n8n | 🟢 P2 | ⏳ Attend P2 |

---

## Prochaines Actions Recommandées

### Pour l'équipe AMENS:

1. **URGENT:** Déboguer l'erreur 500 sur `/professional/{id}`
   - Voir logs Vercel
   - Vérifier requêtes Supabase côté API
   - Tester SSR

2. **Une fois corrigé:** Relancer tests E2E complets

3. **Puis:** Tester SMTP + activer n8n

---

## Résumé Technique

```
┌─────────────────────────────────────────┐
│         AMENS E2E TEST RESULTS          │
├─────────────────────────────────────────┤
│  Homepage        ✅ 200 OK              │
│  Search          ✅ 200 OK              │
│  Auth Page       ✅ 200 OK              │
│  Pro Profile     ❌ 500 ERROR           │ ← BLOCKER
│  Booking         ❌ BLOCKED             │
│  Email/SMTP      ⏳ UNTESTED            │
│  n8n             ⏳ UNTESTED            │
└─────────────────────────────────────────┘

VERDICT: 🔴 NO-GO (Correction requise)
```

---

**Rapport généré:** 2026-02-12 11:52  
**Mise à jour:** V2 - Tests complétés avec preuves techniques  
**Statut:** 🟡 En attente correction bug
