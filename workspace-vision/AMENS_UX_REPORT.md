# Rapport UX & Accessibilité — AMENS
**Date:** 2026-02-12 11:00 CET  
**Scope:** Accessibilité, UX, Performance perçue  
**Statut:** 🟡 Phase 1 complétée — Corrections mineures requises

---

## Executive Summary

L'application AMENS dispose d'une **base d'accessibilité solide** grâce à l'utilisation des composants Radix UI qui implémentent les patterns ARIA standards. Les principaux éléments critiques sont en place (labels, alt text, lang, structure sémantique).

**Score estimé:** 85/100 (WCAG 2.1 AA partiellement conforme)  
**Gap to 90+:** Corrections mineures identifiées ci-dessous.

---

## ✅ Forces & Bonnes Pratiques

### 1. Foundation Technique
- **Radix UI primitives** — Composants headless avec ARIA intégré
- **Label association** — Tous les inputs ont des labels liés via `htmlFor`
- **Alt text** — Présent sur les images (logo, avatars)
- **HTML lang** — Défini sur `fr` pour lecteurs d'écran
- **Semantic HTML** — Utilisation correcte de `<main>`, `<header>`, `<nav>`

### 2. Components Accessibles

#### OnboardingStepper.tsx ⭐ Excellent
```tsx
// ARIA implementés:
aria-current={isCurrent ? "step" : undefined}
aria-valuenow={currentStep}
aria-valuemin={1}
aria-valuemax={defaultSteps.length}
aria-label={`Progression: étape ${currentStep} sur ${steps.length}`}
aria-hidden="true" // sur les icônes décoratives
```

#### Header.tsx ⭐ Bon
```tsx
// Mobile menu accessible:
aria-label={isMobileMenuOpen ? "Fermer le menu" : "Ouvrir le menu"}
aria-expanded={isMobileMenuOpen}
aria-controls="mobile-menu"

role="navigation"
aria-label="Menu mobile"
```

#### Form Components ⭐ Correct
- Labels liés par `id`/`htmlFor`
- Champs requis marqués avec `required`
- Icônes décoratives avec `aria-hidden="true"`

### 3. Loading States (Skeletons)
- `Skeleton.tsx` — Composant générique avec animation pulse
- `DashboardStatsSkeleton.tsx` — Layout spécifique dashboard
- Améliore le LQI (Live Quality Index) et réduit les CLS

### 4. Error Boundaries
- `ErrorBoundary.tsx` implémenté
- Protection sur layout onboarding
- Fallback UI définie

---

## ⚠️ Points d'Attention

### P1 — Critique (bloquant pour audit 90+)

#### 1. Skip Navigation Link
**Problème:** Aucun lien "Aller au contenu principal"  
**Impact:** Navigation clavier fastidieuse (repetitive tabbing)  
**Fix:**
```tsx
// Dans layout.tsx:
<a href="#main-content" className="sr-only focus:not-sr-only">
  Aller au contenu principal
</a>
<main id="main-content">{children}</main>
```

#### 2. Form Error Announcements
**Problème:** Erreurs de formulaire non annoncées aux screen readers  
**Impact:** Utilisateurs non-voyants ne perçoivent pas les erreurs  
**Fix:**
```tsx
// Ajouter aria-live region:
<div aria-live="polite" aria-atomic="true" className="sr-only">
  {formError}
</div>
```

#### 3. Color Contrast (à vérifier)
**Zones de risque:**
- Texte gris sur fond blanc (`text-gray-400`, `text-gray-500`)
- Muted foreground (`--muted-foreground: 220 8% 46%`)

**TODO:** Vérifier ratios avec [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)

---

### P2 — Amélioration

#### 4. AuthForm Toggle Button
**Problème:** Bouton switch login/signup manque d'état ARIA  
**Fix:**
```tsx
<button
  type="button"
  onClick={() => setIsLogin(!isLogin)}
  aria-pressed={!isLogin}
  aria-expanded={true} // si contenu change
>
  {isLogin ? "Pas encore de compte ?" : "Déjà un compte ?"}
</button>
```

#### 5. Focus Visible Enhancement
**Problème:** Outline focus parfois subtil  
**Fix:** Renforcer styles focus:
```css
*:focus-visible {
  outline: 2px solid var(--ring);
  outline-offset: 2px;
}
```

---

### P3 — Nice-to-have

#### 6. ARIA Landmarks
Améliorer structure avec landmarks explicites:
```tsx
<header role="banner">
<nav role="navigation" aria-label="Principale">
<main role="main">
<footer role="contentinfo">
```

#### 7. Headings Hierarchy
Vérifier niveaux H1-H6 logiques sur chaque page.

---

## 📋 Checklist Actions Code

### Fichiers à modifier:

1. **src/app/layout.tsx**
   - [ ] Ajouter skip navigation link
   - [ ] ARIA landmarks sur header/main

2. **src/components/auth/AuthForm.tsx**
   - [ ] aria-pressed sur toggle button
   - [ ] aria-live pour erreurs

3. **src/app/globals.css**
   - [ ] Renforcer focus-visible styles

4. **Tests à ajouter:**
   - [ ] axe-core pour tests CI
   - [ ] Navigation clavier (Tab, Shift+Tab, Enter)

---

## 🧪 Recommandations Testing

### Manuel (requis)
- [ ] Navigation clavier complète (Tab, flèches, Enter, Escape)
- [ ] NVDA ou VoiceOver — parcours complet utilisateur
- [ ] Zoom 200% — vérifier pas de perte de fonctionnalité
- [ ] Contraste couleurs — WebAIM tool

### Automatique
```bash
# Lighthouse CI (recommandé)
npm install -g @lhci/cli
lhci autorun

# axe-core React (optionnel)
npm install @axe-core/react
```

---

## 📊 Grille de Score Estimée

| Critère | Score | Poids | Pondéré |
|---------|-------|-------|---------|
| Keyboard Navigation | 90% | 25% | 22.5 |
| Screen Reader Support | 80% | 25% | 20.0 |
| Color Contrast | 85% | 20% | 17.0 |
| Focus Management | 85% | 15% | 12.75 |
| Semantics | 90% | 15% | 13.5 |
| **Total** | | | **~86** |

**Target:** 90+ après corrections P1

---

## 🔧 Quick Wins (30min)

```tsx
// 1. Skip Link — layout.tsx
<a 
  href="#main" 
  className="absolute -top-10 left-4 z-50 bg-white px-4 py-2 
             focus:top-4 transition-all duration-200
             sr-only focus:not-sr-only focus:ring-2 focus:ring-primary"
>
  Aller au contenu
</a>

// 2. Form error announcer — AuthForm.tsx
<div aria-live="polite" className="sr-only">
  {errorMessage}
</div>

// 3. Focus visible — globals.css
:focus-visible {
  outline: 2px solid hsl(var(--ring));
  outline-offset: 2px;
}
```

---

## Conclusion

**État:** Bonne base, corrections mineures nécessaires  
**Priorité:** P1 items bloquent le score 90+  
**Effort estimé:** 2-4 heures pour corrections P1+P2  
**Prochaine étape:** Implémenter skip navigation + form announcements

---

*Rapport généré par Vision Agent — Session: vision-amens-check*