# Backlog Général — DreamTeam

## AgentViz — Points d'Audit

### 🔴 Priority Haute
- [[RESOLU] [Vision] XSS dans les bulles de chat | Messages non sanitizés | High
- [[RESOLU] [Vision] Pas de CSP dans Electron | Risque XSS | High
- [[RESOLU] [Vision] Race condition abort controller | Perte requêtes | High
- [Vision] Timestamps parsing failure | Perte messages | High
- [Vision] Memory leak animations | Babylon pas nettoyé | High

### 🟡 Priority Moyenne
- [Vision] Pas de error boundary | App crash si Babylon crash | Medium
- [Vision] Polling inconditionnel | Waste CPU | Medium
- [Vision] Pas de validation JSON | Crash potentiel | Medium

### 🟢 Priority Basse
- [Vision] Pas de tests unitaires | Zéro coverage | Low
- [Vision] M5 non terminé | Production Loop pas implémenté | Low

---

## Amens — Points d'Audit

### 🔴 Priority Haute
- [builder] RLS policies | Pas de Row Level Security | High
- [builder] Rate limiting | Pas de rate limiting | High
- [builder] Validation inputs | Client only | High
- [builder] Stripe webhooks | Non vérifiés | High
- [builder] Logs erreurs | Pas centralisés | High
- [architect] Architecture DB | Pas d'index optimaux | High

### 🟡 Priority Moyenne
- [builder] Tests E2E | Zéro test | Medium
- [builder] Optimisation images | Non optimisées | Medium
- [builder] SEO | Meta tags manquantes | Medium
- [builder] Error handling | Incohérent | Medium
- [hunter] Acquisition | Pas de funnel conversion | Medium

### 🟢 Priority Basse
- [builder] Code duplication | Duplication UI | Low
- [builder] Types TypeScript | Pas stricts | Low

---

## ProspectWorkflow — Points d'Audit

### 🔴 Priority Haute
- [hunter] Générateur sites M2 | Pas implémenté | High
- [hunter] SMS Twilio M3 | Pas implémenté | High
- [hunter] Retry logic | Pas de retry | High
- [hunter] Error handling | Crash si erreur | High

### 🟡 Priority Moyenne
- [hunter] Dashboard tracking M4 | Pas développé | Medium
- [hunter] Logging | Pas structuré | Medium
- [hunter] CSV encoding | Pas UTF-8 BOM | Medium
- [vision] UX workflow | Améliorable | Medium

### 🟢 Priority Basse
- [hunter] Tests unitaires | Pas de tests | Low

---

## ContinuousImprovement — Points d'Audit

### 🔴 Priority Haute
- [architect] Scripts cron | Pas standardisés | High
- [architect] Monitoring | Pas centralisé | High
- [architect] Alerting | Pas automatique | High

### 🟡 Priority Moyenne
- [architect] Documentation | Pas à jour | Medium
- [architect] Backup | Pas automatique | Medium
- [builder] Scripts | Pas uniformes | Medium

### 🟢 Priority Basse
- [architect] Tests intégration | Pas de CI/CD | Low

---

## Cross-Audits (Round 2-4)

### Vision → Amens
- [vision] Onboarding flow | Complexe pour pros | Medium

### Builder → ProspectWorkflow
- [builder] Code quality | Validation à améliorer | Medium

### Hunter → ContinuousImprovement
- [hunter] Automatisation | Opportunities identification | Medium

### Architect → AgentViz
- [architect] Scalabilité | Performance 3D | High

### Vision → ProspectWorkflow
- [vision] UI/UX | Workflow complex | Medium

### Builder → ContinuousImprovement
- [builder] Templates | Pas de reusable patterns | Medium

### Hunter → AgentViz
- [hunter] Market fit | Features à prioriser | Medium

### Architect → Amens
- [architect] API design | REST pas optimal | High

### Vision → ContinuousImprovement
- [vision] Strategy | Priorisation | Medium

### Builder → AgentViz
- [builder] Code tech debt | Refactoring needed | Medium

### Hunter → Amens
- [hunter] SEO | Backlinks strategy | Medium

### Architect → ProspectWorkflow
- [architect] DB schema | Scalabilité | Medium

---

## AgentViz — Audit Round 4 (Vision → AgentViz) — 2026-02-14

### 🔴 Priority Haute
- [[RESOLU] [Vision] XSS dans ChatBubble | Messages non sanitizés avec dangerouslySetInnerHTML potentiel | High
- [[RESOLU] [Vision] Pas de CSP HTTP Header | Risque injection scripts | High
- [Vision] Memory leak useEffect cleanup | Animations et intervals pas nettoyés | High
- [[RESOLU] [Vision] Race condition AbortController | Ref pas persists entre renders | High
- [Vision] Pas de Error Boundary | Crash Babylon = crash app React entier | High
- [Vision] Validation JSON absente | Crash si live-messages.json malformé | High
- [Vision] Absence contextIsolation | Risque XSS via preload Bridge | High

### 🟡 Priority Moyenne
- [Vision] Polling inconditionnel | Pas de pause quand tab inactive | Medium
- [Vision] Pas de request throttling | Risk DoS si serveur lent | Medium
- [Vision] Performance 3D | Pas de LOD ou occlusion culling | Medium
- [Vision] Pas de loading states | UX dégradée | Medium

### 🟢 Priority Basse
- [Vision] Pas de tests unitaires | Zéro test coverage | Low

---

## Amens — Audit Round 2 (Builder → Amens) — 2026-02-14

### 🔴 Priority Haute
- [Builder] Tests E2E absents | dette technique critique avant scale | High
- [Builder] Error handling | Incohérent entre composants | High
- [Builder] Rate limiting | Implémentation partielle, non testée | High
- [Builder] Stripe webhooks | Signature non vérifiée | High

### 🟡 Priority Moyenne
- [Builder] React.memo manquant | Re-renders inutiles sur ProfessionalCard, BookingSlot | Medium
- [Builder] useMemo/useCallback | Pas d'optimisation React | Medium
- [Builder] Lazy loading | Pas de code splitting par route | Medium
- [Builder] Image optimization | next/image pas utilisé partout | Medium

### 🟢 Priority Basse
- [Builder] Constants file | Magic strings dans le code | Low
- [Builder] Bundle analyzer | Jamais exécuté | Low

---

*Dernière mise à jour: 2026-02-14 23:44*
