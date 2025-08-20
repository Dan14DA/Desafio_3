
# Telecom X — Parte 2 · Predicción de Churn (Versión C · Colab-only)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/USER/Desafio_2_P2C/blob/main/notebooks/TelecomX_P2_colab_alt.ipynb)

> **Versión C** (distinta a A y B): incluye *feature engineering* diferente, **XGBoost** con búsqueda de hiperparámetros, **curvas Lift/Gain**, y selección de umbral combinando **ganancia** y **Youden J**.

## 🎯 Objetivo
Predecir probabilidad de **churn** y priorizar clientes para campañas, **maximizando ganancia** con probabilidades **calibradas** y umbral **óptimo para negocio**.

## 📁 Estructura
```
TelecomX_P2_repo_alt/
├─ README_P2_alt.md
├─ notebooks/
│  └─ TelecomX_P2_colab_alt.ipynb
├─ data/
│  └─ df_limpo.csv              # opcional (si versionas datos)
└─ reports/
   ├─ README_REPORT_P2_alt.md
   ├─ metrics_p2_alt.json
   └─ clientes_en_riesgo_topN_p2_alt.csv
```

## 🔧 Diferencias clave (vs. otras versiones)
- **Feature engineering**: `auto_pay`, `contract_m2m`, `is_dsl`, `is_fiber`, `tenure_bucket` distinto, `charge_density` = MonthlyCharges / (tenure+1).
- **Modelos**: LogisticRegression (balanced), GradientBoosting y **XGBoost** (con `pip install` en Colab).
- **Calibración**: isotónica/platt; se compara **Brier** y **PR-AUC**.
- **Curvas**: **Lift** y **Cumulative Gain**; además de ROC/PR.
- **Umbral**: (1) máxima **ganancia** y (2) **Youden’s J** como referencia operativa.
- Semilla distinta, parámetros de negocio distintos.

## 🛠️ Cómo ejecutar
1. Abre el badge de Colab arriba.
2. Sube `df_limpo.csv` a `/content` o cambia `CSV_PATH` en la primera celda.
3. Ejecuta todo; se generan artefactos en `/content/reports`.

**Dependencias**: `pandas`, `numpy`, `matplotlib`, `scikit-learn (>=1.1)`, `imbalanced-learn` (opcional), **`xgboost`**.

## 🧭 Guía de lectura rápida para negocio
- **PR-AUC** alto ⇒ los top-score concentran churners (campañas más efectivas).
- **Calibración** ⇒ si dice 0.25, ~25% se irán (probabilidad interpretable).
- **Umbral de negocio** ⇒ usa tus `VALUE_RETAIN` y `COST_CONTACT` para decidir a quién contactar.
- **Lift/Gain** ⇒ qué tanto mejor que el azar es contactar a los top-riesgo.

---

> Reemplaza `USER/Desafio_2_P2C` por el repo donde lo subas para que el badge apunte bien.
