# AI-Driven Risk Management & Anomaly Detection

## Descripción del Proyecto
Este proyecto presenta un sistema de gestión de riesgos impulsado por Inteligencia Artificial aplicado a series de tiempo operativas. Utilizando el dataset de demanda de taxis de Nueva York del **Numenta Anomaly Benchmark (NAB)**, se desarrolló un pipeline analítico para aislar y detectar anomalías estructurales severas (shocks exógenos como tormentas de nieve o eventos masivos).

El objetivo principal es proporcionar una herramienta predictiva y visual para la toma de decisiones directivas frente a la volatilidad del mercado operativo y limpiar flujos de datos reales antes de su ingesta en sistemas de inteligencia de negocios.

## Stack Tecnológico
* **Lenguaje:** Python 3.9+
* **Procesamiento de Datos:** Pandas, NumPy
* **Machine Learning:** Scikit-learn (Isolation Forest)
* **Modelado Estadístico:** Statsmodels (Descomposición STL)
* **Visualización:** Plotly (Dashboards interactivos)

## Metodología y Pipeline
1. **Ingesta y Saneamiento Temporal:** Regularización de la serie de tiempo a intervalos de 30 minutos e imputación de datos mediante interpolación lineal temporal para preservar tendencias locales.
2. **Ingeniería de Características Avanzada:** * **Descomposición STL:** Aislamiento del componente residual $Y_t - (T_t + S_t) = R_t$ como variable crítica.
   * **Métricas Actuariales:** Cálculo de Volatilidad Móvil y Valor en Riesgo (VaR al 95%) para establecer umbrales dinámicos.
3. **Modelado No Supervisado:** Entrenamiento de un algoritmo de `Isolation Forest` (con estandarización previa de variables) para identificar patrones anómalos multivariantes.

## Resultados y Desempeño
* El enfoque híbrido (STL + VaR + Isolation Forest) demostró ser altamente eficaz para discriminar ruido de anomalías reales.
* **Métrica Destacada:** El modelo alcanzó un **AUC de 0.85**, confirmando una capacidad discriminatoria robusta para alertas de riesgo operativo.
* Se desplegó un dashboard interactivo que contrasta la predicción de la IA con el comportamiento normal del negocio en tiempo real.

## Estructura del Proyecto
* `data/` : Datasets crudos y procesados.
* `notebooks/` : Entornos de experimentación (EDA y modelado).
* `requirements.txt` : Lista de dependencias del proyecto.

## Getting Started (Guía de Instalación)

Sigue estos pasos para reproducir el entorno y ejecutar el modelo en tu máquina local.

### 1. Clonar el repositorio
```bash
git clone [https://github.com/TU-USUARIO/Machine-learning-UAEMex.git](https://github.com/TU-USUARIO/Machine-learning-UAEMex.git)
cd Machine-learning-UAEMex
