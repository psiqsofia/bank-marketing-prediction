# Predicción de Éxito en Campañas de Marketing Bancario

Este proyecto aplica algoritmos de aprendizaje supervisado para predecir si un cliente aceptará participar en una campaña de marketing telefónica, basado en datos históricos de clientes y campañas.

## 🎯 Objetivo
Desarrollar un modelo de clasificación que prediga la probabilidad de aceptación de una campaña (`y = yes` o `no`) usando un dataset público de marketing bancario.

## 📊 Dataset
- Fuente: [Bank Marketing Data Set - UCI](https://archive.ics.uci.edu/ml/datasets/bank+marketing)
- Variables: Edad, empleo, estado civil, educación, historial crediticio, etc.
- Target: `y` (¿aceptó la campaña?)

## 🔍 Exploración del modelo
Se compararon dos modelos de Random Forest:

| Modelo              | Accuracy | Precision (y=1) | Recall (y=1) | F1-score (y=1) | ¿Incluye `duration`? |
|---------------------|----------|------------------|---------------|----------------|-----------------------|
| Con `duration`      | 90.10%   | 0.70             | 0.31          | 0.43           | ❌ No recomendado     |
| Sin `duration`      | 87.58%   | 0.47             | 0.43          | 0.45           | ✅ Modelo realista     |

> 🔎 Nota: La variable `duration` (duración de la llamada) tiene alta correlación con la respuesta, pero **no está disponible antes de llamar**, por lo que usarla en un modelo predictivo real es incorrecto.

## 🧠 Conclusiones
- Un modelo ético y aplicable debe excluir variables conocidas *solo después* del evento (como `duration`).
- Aunque el accuracy general disminuye al quitar `duration`, el modelo gana en utilidad práctica.
- El F1-score del modelo sin `duration` es más equilibrado, especialmente útil para campañas donde la clase positiva (`yes`) es escasa.

## 📂 Tecnologías
- Python
- Pandas, Scikit-learn, Matplotlib
- Jupyter Notebook

---

¡Gracias por leer! 🌱
