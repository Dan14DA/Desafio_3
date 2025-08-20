# Predicción de Churn - Telecom X

## ¿Qué hace este proyecto?
Predice qué clientes van a cancelar el servicio y ayuda a decidir a cuáles contactar para retenerlos.

## Archivos del proyecto
```
TelecomX_P2_repo/
├─ README.md
├─ TelecomX_P2_colab.ipynb     # El notebook principal
├─ data/
│  └─ df_limpo.csv             # Datos limpios de la Parte 1
└─ reports/                    # Resultados generados automáticamente
   ├─ README_REPORT_P2.md
   ├─ metrics_p2.json
   └─ clientes_en_riesgo_topN_p2.csv
```

## Cómo usar

### Paso 1: Abrir en Google Colab
Haz clic en el botón "Open in Colab" del archivo original.

### Paso 2: Subir datos
Sube el archivo `df_limpo.csv` a la carpeta `/content` en Colab.

### Paso 3: Ejecutar
Ejecuta todas las celdas del notebook. Al final obtendrás:
- Un reporte con los resultados
- Lista de clientes en riesgo para contactar

## ¿Qué hace el análisis?

### Preparación de datos
- Separa variables numéricas (precios, tiempo) y categóricas (tipo contrato, método pago)
- Divide datos en entrenamiento (80%) y prueba (20%)
- Balancea los datos si es necesario

### Modelos que usa
- **Regresión Logística**: Fácil de interpretar
- **Random Forest**: Más complejo pero preciso
- **Gradient Boosting**: El más sofisticado

### Evaluación
- Encuentra el mejor modelo comparando su precisión
- Calcula el umbral óptimo para maximizar ganancias
- Identifica qué variables son más importantes

## Resultados esperados

### Variables importantes (típicamente):
- **Contratos mes a mes**: Mayor riesgo de cancelación
- **Pago con cheque electrónico**: Más propensos a irse
- **Internet por fibra**: Puede tener problemas técnicos
- **Clientes nuevos**: Menor lealtad
- **Cargos altos**: Sensibles al precio

### Recomendaciones de negocio:
1. **Ofrecer contratos anuales** a clientes mes a mes
2. **Promover pago automático** en lugar de cheques
3. **Mejorar soporte técnico** para internet por fibra
4. **Programa especial** para clientes nuevos
5. **Descuentos personalizados** para cargos altos

## Requisitos técnicos
- Python con pandas, numpy, matplotlib, scikit-learn
- Google Colab (recomendado)
- Archivo `df_limpo.csv` de la Parte 1

## Nota importante
Este proyecto usa parámetros de negocio (costo de contactar vs valor de retener) que debes ajustar según tu empresa.

---
*Proyecto académico 2025*