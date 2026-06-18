# WC 2026 Predictor ⚽

Outil de prédiction des matchs de la Coupe du Monde 2026, basé sur :
- **Modèle Poisson-Dixon-Coles** pour les probabilités de score
- **ELO dynamique** (K=60, multiplicateur MoV)
- **Météo en temps réel** via Open-Meteo (gratuit, sans clé)
- **API-Football** pour compositions et cotes live (optionnel)
- **Analyse IA** via Claude (optionnel)

## Accès

👉 **[https://matltg.github.io/wc2026-predictor](https://matltg.github.io/wc2026-predictor)**

## Configuration des clés API

L'application fonctionne sans clé API (données démo intégrées). Pour les données live :

### API-Football (compositions + cotes)
1. Créer un compte gratuit sur [dashboard.api-football.com](https://dashboard.api-football.com)
2. Copier la clé dans l'onglet **Config** de l'app
- Quota : 100 requêtes/jour (gratuit)

### Anthropic API (analyse IA)
1. Créer une clé sur [console.anthropic.com](https://console.anthropic.com/api-keys)
2. Copier la clé `sk-ant-...` dans l'onglet **Config** de l'app
- Sans clé : les prédictions mathématiques restent 100% opérationnelles

## Déploiement GitHub Pages

1. Aller dans **Settings → Pages**
2. Source : **Deploy from a branch**
3. Branch : `main` / `/(root)`
4. Sauvegarder — le site sera disponible en ~30 secondes

## APIs utilisées

| API | Usage | Auth | Gratuit |
|-----|-------|------|---------|
| [Open-Meteo](https://open-meteo.com) | Météo temps réel | ❌ Aucune | ✅ |
| [API-Football](https://dashboard.api-football.com) | Fixtures + cotes | ✅ Header `x-apisports-key` | ✅ 100 req/j |
| [Anthropic](https://console.anthropic.com) | Analyse IA | ✅ Header `x-api-key` | 💰 Payant |
| [worldcup26.ir](https://worldcup26.ir) | Fallback fixtures | ❌ Aucune | ✅ |
