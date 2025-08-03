# 📊 Challenge TelecomX - Parte 2: Modelos Predictivos de Cancelación de Clientes (Churn)

## 🧠 Objetivo
Desarrollar modelos de machine learning para predecir la cancelación de clientes, identificar las variables más relevantes y proponer estrategias de retención basadas en los resultados.

---

## ⚙️ Modelos Utilizados

### 1. Regresión Logística (con normalización)
- **Acuracia:** 36%
- **Ventajas:** Modelo interpretable, ideal para entender impacto de cada variable.
- **Desventajas:** Bajo rendimiento en recall para la clase "No Canceló", lo que indica **underfitting**.

### 2. Random Forest (sin normalización)
- **Acuracia:** 52%
- **Ventajas:** Captura relaciones no lineales, robusto ante outliers, buen balance en las métricas.
- **Desempeño general:** **Superior** a Regresión Logística.

> Se utilizó **SMOTE** para tratar el desbalance de clases y mejorar la sensibilidad hacia los clientes que cancelan.

---

## 📈 Métricas de Evaluación

| Modelo              | Accuracy | Precision | Recall | F1-Score |
|---------------------|----------|-----------|--------|----------|
| Regresión Logística | 0.36     | 0.75      | 0.36   | 0.31     |
| Random Forest       | 0.52     | 0.74      | 0.52   | 0.53     |

---

## 🔍 Principales Variables que Impactan en la Cancelación

### Según Random Forest:

| Variable                     | Descripción                                           |
|-----------------------------|-------------------------------------------------------|
| `InternetService_Fiber optic` | Asociado con mayor tasa de cancelación               |
| `OnlineSecurity_No`         | Falta de seguridad online correlaciona con churn     |
| `TechSupport_No`            | Clientes sin soporte técnico cancelan más            |
| `Contract_Month-to-month`   | Contratos mensuales tienen mayor rotación            |
| `tenure`                    | Antigüedad baja = mayor probabilidad de cancelar     |
| `MonthlyCharges`            | Cargos mensuales altos → mayor riesgo de cancelación |
| `TotalCharges`              | Clientes con pocos cargos (recién ingresados) cancelan más |

---

## 📌 Conclusiones

- El **modelo Random Forest** fue el más eficaz, superando en todas las métricas a la Regresión Logística.
- La **cancelación de clientes** se asocia fuertemente con:
  - Tipo de contrato
  - Cargos mensuales
  - Antigüedad del cliente
  - Servicios adicionales (seguridad online y soporte técnico)

---

## 💡 Propuestas de Retención

- 🔒 **Bonificaciones de retención** para clientes nuevos (`tenure < 12 meses`)
- 💻 **Promocionar servicios de valor agregado** (seguridad online, soporte técnico)
- 📆 **Incentivar contratos de largo plazo** (trimestral o anual)
- 💸 **Revisar estructura de precios** para clientes con altos `MonthlyCharges`

---

## 🧪 Tecnologías y Librerías

- `pandas`, `numpy`
- `scikit-learn`
- `imbalanced-learn (SMOTE)`
- `matplotlib`, `seaborn`

---

## ✅ Estado del Proyecto
✔ Parte 1 completada: EDA, limpieza y subida a GitHub  
✔ Parte 2 completada: modelos, métricas, visualización y conclusión  
🔜 Futura mejora: evaluación con más modelos (XGBoost, SVM) y análisis SHAP.

---

## 📁 Estructura del Proyecto

