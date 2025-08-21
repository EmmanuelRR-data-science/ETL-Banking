# Bank Marketing Dashboard & Machine Learning

## 📌 Descripción
Este proyecto implementa un flujo completo de análisis y predicción para el dataset de marketing bancario. Se entrenó un modelo de **Random Forest** para predecir la probabilidad de que un cliente acepte un producto bancario, y se prepararon los datos para visualización en **Looker Studio** mediante **BigQuery** en Google Cloud Platform (GCP).

El objetivo principal es demostrar competencias en **Data Analytics, Business Intelligence, Cloud y Machine Learning**, cumpliendo con estándares de la industria.

---

## 🛠 Tecnologías y Herramientas
- **Lenguajes:** Python, SQL  
- **Librerías Python:** pandas, numpy, scikit-learn, matplotlib, seaborn  
- **Cloud:** Google Cloud Platform (BigQuery, Google Cloud Storage)  
- **Machine Learning:** Random Forest, Regresión Logística  
- **BI / Visualización:** Looker Studio (Google Data Studio)  
- **Control de versiones:** Git / GitHub  

---

## 🔹 Flujo del Proyecto

1. **Carga de Datos:**  
   - Dataset: [Banking Dataset - Marketing Targets (Kaggle)](https://www.kaggle.com/uciml/bank-marketing)
   - Se procesan los CSV `train.csv` y `test.csv`.

2. **Preprocesamiento:**  
   - Manejo de valores faltantes.  
   - Codificación OneHot para variables categóricas.  
   - Escalado si es necesario.

3. **Modelado:**  
   - Entrenamiento de **Random Forest** y **Regresión Logística**.  
   - Evaluación con métricas: ROC-AUC, PR-AUC, F1-Score.  
   - Optimización de umbral F1 para clasificación binaria.

4. **Predicciones:**  
   - Generación de `pred_rf` (predicción binaria) y `prob_rf` (probabilidad).  
   - Preparación del DataFrame completo para visualización.

5. **Subida a BigQuery:**  
   - Autenticación en GCP (Colab / Service Account).  
   - Subida del dataset con predicciones, usando **chunks** o CSV vía **Google Cloud Storage** para evitar errores de carga.

6. **Visualización en Looker Studio:**  
   - Conexión a BigQuery.  
   - KPIs principales: Tasa de conversión, contactos totales, duración promedio de campañas.  
   - Gráficos: Distribución de predicciones, matriz de confusión, probabilidades de conversión.  
   - **Dashboard interactivo:** [Ver aquí](https://lookerstudio.google.com/s/iW8KHb9WLew)

---

## 📊 Resultados Clave

- **Random Forest** mostró mejor desempeño que Regresión Logística:
  - ROC-AUC test: ~0.90  
  - PR-AUC test: ~0.60  
  - Mejor umbral F1: ~0.445 → F1-score ~0.59  

- **Variables más importantes:**
  - `poutcome_success`, `month_mar`, `month_jan`, `month_oct`, `month_sep`, etc.

- La tabla final con predicciones (`y`, `pred_rf`, `prob_rf`) se encuentra en **BigQuery** lista para dashboards en Looker Studio.

---

## 📌 Cómo Ejecutar

1. Clonar el repositorio:
```bash
git clone https://github.com/EmmanuelRR-data-science/ETL-Banking.git
cd ETL-Banking

