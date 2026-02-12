# AMENS Rapport Croissance

**Plateforme:** AMENS.fr — Le rendez-vous bien-être, simplifié  
**Mission:** 100 professionnels inscrits en 30 jours  
**Période:** 12 Février → 14 Mars 2026  
**Date du rapport:** 12 Février 2026 — Jour 0 (Setup)

---

## 📊 KPIs Actuels & Projections

### Situation de Départ (Jour 0 — 12/02/2026)

| Métrique | Valeur Actuelle | Objectif J+30 | Progression |
|----------|----------------|---------------|-------------|
| **Professionnels inscrits** | 0 | 100 | 🔄 En cours |
| **Landing page** | ✅ Live | - | ✅ Optimisée |
| **Workflows n8n** | ✅ 3 créés | - | ✅ Opérationnels |
| **Offres créées** | 0 | 250+ (2.5/pro) | 🔄 En cours |
| **RDV pris** | 0 | 75+ (0.75/pro) | 🔄 En cours |
| **Taux d'activation** | N/A | 70% | 📊 À tracker |
| **MRR estimé** | €0 | €870* | 💰 Projection |

\* *Hypothèse : 30% des pros passent au plan payant après 3 mois gratuits*  
\* *À J+90 : 30 pros × €29/mois = €870 MRR initial*

### Projections Trajectoire

```
┌─────────────────────────────────────────────────────────────────┐
│  CROISSANCE PROFESSIONNELS (J+0 à J+30)                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Pros    │                                                      │
│  cumulés │                                          ●─── 100    │
│     100  │                                    ●──────┘          │
│      90  │                              ●────┘                  │
│      75  │                        ●────┘                        │
│   60 ────┼────────────────●────────┘                            │
│      45  │           ●───┘                                     │
│      35  │      ●───┘                                          │
│      20  │ ●────┘                                              │
│      15 ─┼┘                                                    │
│       0 ─┴────────────────────────────────────────────────────  │
│           0   5  10  15  20  25  30                            │
│                        Jours                                    │
└─────────────────────────────────────────────────────────────────┘
```

| Jour | Pros Cumulés | Offres | RDV/mois | Canal Principal |
|------|-------------|--------|----------|-----------------|
| 0 | 0 | 0 | 0 | Setup |
| 5 | 15 | 30 | 8 | LinkedIn |
| 10 | 35 | 80 | 25 | LinkedIn + Email |
| 15 | 55 | 140 | 45 | Email + Référal |
| 20 | 75 | 180 | 60 | Viral + Partenariats |
| 25 | 90 | 220 | 70 | Multi-canal |
| **30** | **100** | **250** | **75** | **🎯 OBJECTIF** |

### Segments Cibles

| Métier | Localisation | Pain Point | Message Clé |
|--------|-------------|------------|-------------|
| **Coachs sportifs** | Grandes villes (Marseille, Paris, Lyon, Bordeaux, Toulouse) | Gestion agenda galère | "Vos clients bookent en ligne" |
| **Kinésithérapeutes** | IDF, PACA, Rhône | No-shows, appels permanents | "Rappels auto SMS/email" |
| **Ostéopathes** | Toute France | Réservations téléphone | "Disponibilités temps réel" |
| **Yoga/Pilates** | Urbain trendy | Instagram booking | "Lien bio qui convertit" |

---

## 💰 Unit Economics

### Pricing Strategy

| Plan | Prix | Détails | Public |
|------|------|---------|--------|
| **Offre Lancement** | €0/mois | 3 mois gratuits | Tous les pros |
| **Jeunes Diplômés** | €0/mois | 6 mois gratuits | Code promo écoles |
| **Mensuel** | €29/mois | Annulation anytime | Standard |
| **Annuel** | €290/an | ≈ €24/mois (-17%) | Engagés |
| **Early-bird** | €19/mois | 6 mois -35% | Conversion pré-J+90 |

### CAC (Customer Acquisition Cost) — Estimations

| Canal | Coût/prospect | Conversion | CAC estimé | Source |
|-------|---------------|------------|------------|--------|
| **LinkedIn DM** | €0 (temps interne) | 8-12% | €15-25* | n8n workflow |
| **Email Cold** | €0.50/prospect | 2-4% | €12-25 | Apollo/Mailgun |
| **SEO Content** | €0 | 15-20% | €5-10* | Blog organique |
| **Referral** | €0 (rétrocession 1 mois) | 25-35% | €20-30 | Viral loop |
| **Partenariats écoles** | €0 | 20-30% | €10-15* | IFMK/STAPS |
\* *Coûts en temps estimés (interne) — saler main libre*

**CAC moyen estimé: €15-20**  
**Target CAC: <€50** (marge de sécurité confortable)

### LTV (Lifetime Value)

```
Paramètres de calcul:
├── Prix moyen: €265/an (mix 70% annuel @ €290 + 30% mensuel @ €348)
├── Churn année 1: 8% mensuel
├── Churn année 2+: 5% mensuel
├── Durée vie moyenne: 18 mois
└── LTV = €265 × 1.5 ans = €397.50

Scénarios LTV:
├── Pessimiste (churn 10%): €265 × 1 an = €265
├── Réaliste (churn 8% → 5%): €265 × 1.5 = €397
└── Optimiste (churn 5%): €265 × 2 = €530
```

| Scénario | LTV | LTV/CAC Ratio | Health |
|----------|-----|---------------|--------|
| Pessimiste | €265 | 13:1 | ✅ Excellent |
| Réaliste | €397 | 20:1 | ✅ Excellent |
| Optimiste | €530 | 26:1 | ✅ Excellent |

✅ **LTV/CAC > 3:1 = Unit economics saines**  
✅ **Ratio cible : >5:1** — *Nous sommes à 20:1, très confortable*

### Payback Period

| Scénario | Période de remboursement | Notes |
|----------|-------------------------|-------|
| Avec plan annuel | 1-2 mois après activation | Très rapide |
| Avec plan mensuel | 2 mois après activation | Standard |
| Compte tenu gratuité | J+120 à J+150* | Free period inclus |

\* *Les 3 mois gratuits retardent le payback effectif*

### Break-even Analysis

```
Coûts fixes estimés (mensuels):
├── Infrastructure (hosting, DB, CDN): €150
├── Outils (n8n, email, analytics): €100
├── Comms (Mailgun/SendGrid ~5k emails): €50
└── Total coûts techniques: €300

Point de rentabilité:
├── Plan mensuel: 11 pros payants (11 × €29 = €319)
├── Plan annuel: 2 pros payants (2 × €290/12 = €48) + mensuels
└── Objectif break-even: 15 pros payants d'ici J+120
```

---

## 🚀 Growth Playbooks

### Matrice Canaux

| Canal | Tactique | Coût | Effort | Impact | Priorité | Status |
|-------|----------|------|--------|--------|----------|--------|
| **LinkedIn** | Prospection DM ciblée (coachs/kinés/ostéos) | €0 | Moyen | Élevé | ⭐⭐⭐ **P1** | ✅ Prêt |
| **Email** | Cold outreach séquencé (5 emails/14j) | ~€50/mois | Faible | Moyen | ⭐⭐ **P2** | ✅ Prêt |
| **SEO** | Content yoga/pilates + fiches métier | €0 | Élevé | Long terme | ⭐⭐ **P2** | 🔄 En cours |
| **Referral** | Programme "Parrainage: 1 mois offert" | €0 | Faible | Élevé (viral) | ⭐⭐⭐ **P1** | 🔄 J+14 |
| **Partenariats** | Écoles kiné/sport (IFMK, STAPS) | €0 | Élevé | Très Élevé | ⭐⭐⭐ **P1** | 🔄 Identif. |
| **Communautés** | Groupes Facebook pros santé/sport | €0 | Moyen | Moyen | ⭐⭐ **P2** | ⏳ À démarrer |
| **Presse locale** | Pitch médias régionaux | €0 | Moyen | Moyen | ⭐ **P3** | ⏳ En attente |
| **Webinars** | "Digitaliser votre pratique" | €0 | Élevé | Élevé | ⭐⭐ **P2** | ⏳ À planifier |

### Détails par Canal

#### 1. LinkedIn Prospection (P1 — Jour 1-30) ✅ **ACTIF**
- **Cible:** Coachs sportifs, kinésithérapeutes, ostéopathes indépendants
- **Géographie:** Marseille, Paris, Lyon, Bordeaux, Toulouse
- **Volume:** 10 connexions/jour → 300/mois
- **Script n8n:** 
  ```
  "Bonjour {{prenom}}, je vois que vous êtes {{metier}} à {{ville}}.
  Une question: vos clients peuvent-ils prendre RDV en ligne 24/7 ?
  AMENS.fr simplifie la prise de rendez-vous pour les pros du sport..."
  ```
- **Follow-up:** J+3 si pas de réponse
- **Conversion attendue:** 8-12% → 25-35 inscriptions
- **Workflow:** `/n8n_workflows/linkedin_prospection.json`

#### 2. Email Cold Outreach (P2 — Jour 7-30)
- **Liste:** Annuaires kiné, coachs, ostéos (scraping soigné)
- **Séquence n8n:** 
  - Email 1 (J0): "Votre agenda en ligne ?"
  - Email 2 (J+3): Cas client réussite
  - Email 3 (J+7): Dernière chance
  - Email 4 (J+14): Offre exclusive
- **Outil:** Mailgun (~€50/mois pour 5k emails)
- **Volume:** 200 emails/semaine
- **Conversion attendue:** 2-4% → 16-32 inscriptions
- **Tracking:** UTM params dans les liens

#### 3. SEO Content (P2 — Jour 1-30+)
- **Articles cibles:**
  - "Comment réduire vos no-shows de 80%"
  - "Logiciel prise de rendez-vous kinéthérapie"
  - "Meilleures plateformes booking yoga 2026"
- **Keywords:** "outil gestion RDV kiné", "agenda en ligne coach sportif"
- **Délai résultats:** 3-6 mois (long terme)

#### 4. Programme Referral (P1 — Jour 14)
- **Offre:** "Parrainez un confrère, gagnez 1 mois offert sur votre abonnement"
- **Trigger:** Pro actif (5+ RDV pris)
- **Workflow:** Email J+30 → lien unique par pro
- **K-factor visé:** 0.3 (chaque pro amène 0.3 nouveau pro)
- **Impact viral:** Potentiellement 30% des nouvelles inscriptions

#### 5. Partenariats Écoles (P1 — Jour 10-30)
- **Cibles:** 
  - IFMK (Instituts Formation Masso-Kiné) — Marseille, Paris
  - Facultés STAPS — Aix-Marseille, Lyon, Paris
  - Écoles ostéopathie — CEFO, ISO)
- **Proposition:** "6 mois gratuits pour vos diplômés 2025-2026"
- **Bénéfice école:** Service aux étudiants, partenariat tech
- **Code promo:** "STUDENT2026" → 6 mois gratuits
- **Volume potentiel:** 50-100 inscriptions par école partenaire

---

## 📅 30-Day Growth Plan

### Semaine 1: Foundation (12/02 → 18/02)
**🎯 Objectif: 15-20 inscriptions**

| Jour | Date | Action | Livrable | Metric |
|------|------|--------|----------|--------|
| J+0 | 12/02 | ✅ Rapport croissance créé | `AMENS_RAPPORT_CROISSANCE.md` | - |
| J+1 | 13/02 | 🔄 Lancer workflow LinkedIn | 10 connexions/jour | 10 contacts |
| J+2 | 14/02 | 🔄 Continuer LinkedIn + setup Mailgun | Config email | 20 contacts |
| J+3 | 15/02 | 🔄 Landing A/B test headline | 2 variants | Visites: 50+ |
| J+4 | 16/02 | 🔄 Créer liste email prospects | 200 contacts qualifiés | - |
| J+5 | 17/02 | 🔄 LinkedIn + premiers emails | 10 connexions + 50 emails | 35 contacts |
| J+6 | 18/02 | 🔄 Follow-ups LinkedIn | Réponses qualifiées | - |
| **J+7** | **19/02** | **📊 Review Semaine 1** | **Analytics + ajustements** | **Target: 15-20 pros** |

### Semaine 2: Scale (19/02 → 25/02)
**🎯 Objectif: 35-45 cumulé (+20-25)**

| Jour | Action | Output |
|------|--------|--------|
| J+8 | 15 connexions LinkedIn/jour | 45 connexions |
| J+9 | Email drip launch (200 contacts) | 200 emails envoyés |
| J+10 | Setup referral program (back+front) | Programme actif |
| J+11 | Première approche IFMK Marseille | Contact établi |
| J+12 | Follow-ups + qualification | 40+ réponses |
| J+13 | Optimisations messages (A/B) | Meilleurs CTAs |
| **J+14** | **📊 Review Semaine 2** | **Target: 35-45 pros** |

### Semaine 3: Optimisation (26/02 → 04/03)
**🎯 Objectif: 60-75 cumulé (+25-30)**

| Jour | Action | Output |
|------|--------|--------|
| J+15 | Scale LinkedIn à 20/jour | 60 connexions |
| J+16 | Publish SEO Article #1 | "Réduire no-shows 80%" |
| J+17 | Relance écoles + partenariats | 3 partenariats pipeline |
| J+18 | Email sequence #2 + segmentation | Better targeting |
| J+19 | Activation pros existants | 40+ offres créées |
| J+20 | Webinar "Digitaliser pratique" | Lead gen |
| **J+21** | **📊 Review Semaine 3** | **Target: 60-75 pros** |

### Semaine 4: Sprint Final (05/03 → 14/03)
**🎯 Objectif: 100 cumulé (+25-40)**

| Jour | Action | Output |
|------|--------|--------|
| J+22 | Blitz LinkedIn + communautés | 80 connexions |
| J+23 | Référal boost + viral push | Viral loop actif |
| J+24 | SEO Article #2 | Authority building |
| J+25 | Demos live + calls 1-to-1 | Conversions finales |
| J+26 | Derniers pushes + urgences | Fermeture |
| J+27-13 | Squeeze + onboarding acceléré | Last mile |
| **J+30** | **🎯 OBJECTIF 100 PROS ATTEINT** | **Célébration !** |

### Récap Planning Gantt

```
Semaine  │     1       │     2       │     3       │     4      
─────────┼─────────────┼─────────────┼─────────────┼─────────────
LinkedIn │████████████│████████████│████████████│████████████
Email    │    ░░░░████│████████████│████████░░░░│░░░░████░░░░
Referral │░░░░░░░░░░░░│░░░░░░██████│████████░░░░│░░░░░░░░░░░░
SEO      │████░░░░░░░░│░░░░░░░░░░░░│░░░░░░██████│████░░░░░░░░
Parte-   │░░░░░░░░░░░░│░░░░░░░░░░░░│████░░░░░░░░│░░░░████████
 nariats │             │             │             │            
─────────┼─────────────┼─────────────┼─────────────┼─────────────
Cumul    │    15-20    │    35-45    │    60-75    │  🎯 100     
```

---

## 📈 Metrics à Tracker (Dashboard)

### Acquisition

| Métrique | Fréquence | Cible J+30 | Outil | Owner |
|----------|-----------|------------|-------|-------|
| Signups/jour | Quotidien | 3-5 | Analytics interne | @saler |
| Signups/semaine | Hebdo | 20-30 | Dashboard | @saler |
| Sources acquisition | Hebdo | % par canal | UTM/Referrer | @saler |
| CAC réel | Hebdo | <€25 | Sheets/DB | @scaler |
| Visites landing | Quotidien | 500/jour | Google Analytics | @saler |
| LinkedIn connection rate | Quotidien | >20% | n8n logs | @saler |
| Email open rate | Par campagne | >25% | Mailgun | @saler |
| Email CTR | Par campagne | >5% | Mailgun | @saler |

### Activation

| Métrique | Fréquence | Cible | Définition | Status |
|----------|-----------|-------|------------|--------|
| **% création première offre** | Quotidien | 60% | Pros ayant créé ≥1 offre | 🔄 Tracker |
| **% configuration agenda** | Quotidien | 70% | Pros avec dispo définies | 🔄 Tracker |
| **% connexion calendrier** | Quotidien | 50% | Google/Outlook/Apple sync | 🔄 Tracker |
| **% premier RDV reçu** | Hebdo | 40% | 1er RDV via AMENS | 🔄 Tracker |
| Time-to-first-value | Hebdo | <48h | Temps création offre | 🔄 Tracker |

### Engagement

| Métrique | Fréquence | Cible | Note |
|----------|-----------|-------|------|
| RDV pris/semaine | Hebdo | 20+ croissant | Volume |
| Offres actives | Hebdo | 150+ | >0 dispo |
| Taux conversion visite→signup | Hebdo | 5%+ | Landing CVR |
| Taux conversion offre→RDV | Hebdo | 30%+ | Activation |

### Retention

| Métrique | Fréquence | Cible | Définition |
|----------|-----------|-------|------------|
| **Retention Day-7** | Quotidien | 50%+ | Reconnect J+7 |
| **Retention Day-30** | Mensuel | 40%+ | Actif J+30 |
| Churn rate | Mensuel | <10% | Pros partis/Total |
| NPS Score | Mensuel | >30 | Survey pro |

### Revenue (À J+90+)

| Métrique | Fréquence | Projection | Note |
|----------|-----------|------------|------|
| **MRR** | Mensuel | €0→€870 | À J+90 |
| **ARR** | Mensuel | €0→€10,440 | Run rate |
| % conversion free→payant | Mensuel | 30%+ | Après 3 mois |
| Revenue/pro (ARPU) | Mensuel | €265/an | LTV driver |
| Early-bird revenue | Mensuel | % à €19/mois | J+60-90 |

### Marketing

| Métrique | Fréquence | Cible |
|----------|-----------|-------|
| Taux ouverture emails | Par campagne | 25%+ |
| Taux clic emails | Par campagne | 5%+ |
| Taux réponse LinkedIn | Hebdo | 15%+ |
| Referral rate | Hebdo | 15%+ des inscriptions |
| Partenariats écoles | Mensuel | 2-3 actifs |

---

## 💡 Recommendations Stratégiques

### 1. 🚀 Focus LinkedIn (ROI Immédiat) — PRIORITÉ MAX
> **Investir 70% du temps sur LinkedIn prospection** les 30 premiers jours. Canal le plus efficace en B2B pros santé/sport avec CAC quasi-nul et conversion 8-12%.
>
> **Actions concrètes:**
> - 10 connexions/jour minimum (300/mois)
> - Follow-up systématique J+3
> - Tracker taux de réponse dans n8n logs
> - Optimiser script basé sur early responses

### 2. 🔄 Activer le Referral ASAP — LEVIER VIRAL
> **Lancer le programme de parrainage dès J+14**. Avec un CAC quasi-nul et un potentiel viral élevé, c'est le canal le plus scalable à long terme.
>
> **Actions concrètes:**
> - Trigger: Pro avec 5+ RDV pris
> - Offre: "1 mois offert par filleul"
> - Tracking: Lien unique par pro (UTM)
> - K-factor visé: 0.3 (30% viral lift)

### 3. 🎓 Partenariats Écoles = Levier Structurel
> **Prioriser les contacts IFMK/STAPS** dès la semaine 2. Un partenariat école peut rapporter 50-100 inscriptions d'un coup avec une crédibilité institutionnelle.
>
> **Écoles prioritaires:**
> - IFMK Marseille (proximité)
> - STAPS Aix-Marseille (volume)
> - Écoles ostéopathie régionales

### 4. ⚡ Optimiser l'Activation (Critical Path)
> **Le vrai succès = pros actifs, pas juste inscrits**. Mettre en place:
> - Onboarding email séquencé (J+0, J+1, J+3, J+7) — ✅ DÉJÀ PRÊT
> - Template offres pré-remplies par métier
> - Support chat/reactif les premiers jours
> - **Target activation:** 70% créent leur première offre

### 5. 💰 Pricing Strategy Validation
> **Tester la résistance au prix** avec une cohorte de 20 pros avant d'annoncer officiellement. Observer:
> - Taux conversion vers payant à J+90
> - Préférence mensuel vs annuel
> - Feedback prix (trop cher/juste)
> - Early-bird offer (6 mois à €19) pour accélérer

### 6. ⚠️ Risques & Mitigations

| Risque | Probabilité | Impact | Mitigation | Owner |
|--------|-------------|--------|------------|-------|
| Moins de 100 pros inscrits | Moyen | Élevé | Doubler effort LinkedIn à J+15 | @saler |
| Activation faible (<30%) | Moyen | Élevé | Calls 1-to-1 avec chaque pro | @saler |
| Churn élevé post-gratuité | Moyen | Élevé | Créer valeur avant J+90 | @scaler |
| LinkedIn rate limiting | Moyen | Moyen | Espacer les connexions | @saler |
| Concurrence Doctolib | Faible | Moyen | Différenciation sport/spécialisation | @scaler |

---

## 🎯 Next Steps Immédiats (Today / J+1)

1. ✅ **Aujourd'hui (J+0):** Créer rapport croissance — **FAIT**
2. 🔄 **Demain (J+1):** Lancer workflow LinkedIn n8n — **10 connexions**
3. 🔄 **J+2:** Setup compte Mailgun pour cold email
4. 🔄 **J+3:** A/B test headline landing page
5. 🔄 **J+4:** Créer liste 200 prospects email
6. 🔄 **J+7:** Première review hebdo (metrics)

---

## 📚 Références & Assets

### Documents existants (workspace-saler)
- **Stratégie:** `/projects/amens/STRATEGY_VENTES.md`
- **Progress J1:** `/projects/amens/PROGRESS_J1.md`
- **Landing pro:** `/projects/amens/landing_pages/professionnels.html`
- **Emails:** `/projects/amens/email_templates/nurture_sequence.html`
- **Workflow n8n:** `/projects/amens/n8n_workflows/linkedin_prospection.json`

### Ce rapport (workspace-scaler)
- **Rapport complet:** `workspace-scaler/AMENS_RAPPORT_CROISSANCE.md`
- **Progress tracker:** `inbox/scaler_amens_progress.md`

---

*Document créé le 12/02/2026 — Version 1.0*  
*Auteur: @scaler*  
*Collaboration: @saler (main libre)*  
*Prochaine review: J+7 (19/02/2026)*
