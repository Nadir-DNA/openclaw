# DISPATCH MISSIONS — AMENS Improvements
## Distribution par agent (exclu: @innovator business tasks)

---

## @architect — MISSION CRITIQUE
**Environnement:** /home/nadir/.openclaw/workspace-architect/amens-improvements
**Autonomie:** GO immédiat

### Tasks:
1. **Créer middleware.ts** — Auth guard routes protégées
2. **Ajouter indexes SQL** — Performance queries
3. **Setup rate limiting** — Vercel KV prototype
4. **Document RLS policies** — Audit sécurité

### Output:
- `middleware.ts` fonctionnel
- `migrations/20250211_indexes.sql`
- `lib/rate-limit.ts` prototype
- `SECURITY_AUDIT.md`

---

## @builder — MISSION CRITIQUE  
**Environnement:** /home/nadir/.openclaw/workspace-builder/amens-improvements
**Autonomie:** GO immédiat

### Tasks:
1. **Setup test framework** — Vitest + Testing Library
2. **Tests E2E critiques** — Login → Booking flow complet
3. **Error Boundaries** — Wrapper layouts + Fallback UI
4. **React.memo optimization** — ProfessionalCard, BookingSlot

### Output:
- `vite.config.ts` + setup tests
- `e2e/auth-booking.spec.ts` (Playwright)
- `components/ErrorBoundary.tsx`
- Optimized components with memo

---

## @vision — MISSION CRITIQUE
**Environnement:** /home/nadir/.openclaw/workspace-vision/amens-improvements
**Autonomie:** GO immédiat

### Tasks:
1. **A11y audit** — Lighthouse score > 90
2. **ARIA labels** — Screen readers support
3. **Onboarding stepper** — Progressive disclosure
4. **Micro-interactions** — Loading skeletons + feedback

### Output:
- `a11y-fixes.patch` — ARIA labels + contrast
- `components/OnboardingStepper.tsx`
- `components/ui/Skeleton.tsx`
- `UI_IMPROVEMENTS.md`

---

## @manager — COORDINATION
**Action:** Monitor progress, consolidate reports

---

## RÈGLES STRICTES:
- ✅ Chaque agent bosse dans SON workspace isolé
- ✅ Tests avant commit
- ✅ GO immédiat — pas d'attente approbation
- ❌ PAS @innovator sur cette phase (business stratégie)
- ❌ PAS de modif en production (copier amens, travailler sur copie)

---

## COMMANDS DE DÉMARRAGE:
```bash
# Architect
cd /home/nadir/.openclaw/workspace-architect
cp -r ../workspace/amens ./amens-improvements
cd amens-improvements
code .

# Builder  
cd /home/nadir/.openclaw/workspace-builder
cp -r ../workspace/amens ./amens-improvements
cd amens-improvements
npm install

# Vision
cd /home/nadir/.openclaw/workspace-vision
cp -r ../workspace/amens ./amens-improvements
cd amens-improvements
npm run dev
```

---

**Lancement:** IMMÉDIAT
**Deadline:** 24h pour première itération
**Communication:** Rapports dans `/reports/` de chaque workspace