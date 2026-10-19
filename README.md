# Pronóstico al Día 3

Tablero interactivo que estima, para un paciente gravemente enfermo, el riesgo de morir durante la hospitalización y la fecha probable de fallecimiento a partir de su estado clínico al tercer día de hospitalización.

Es el componente de comunicación del proyecto final de la Unidad 2 de SC3314 Inteligencia Artificial (Universidad de Monterrey), basado en el conjunto de datos SUPPORT2 del UCI Machine Learning Repository.

## Qué muestra

- **Riesgo de muerte durante la hospitalización**, con el grupo de riesgo del paciente y la mortalidad observada en ese grupo en el conjunto de prueba.
- **Fecha estimada de fallecimiento**: el día en que el riesgo acumulado alcanza 50 %, la ventana de tiempo más probable y la curva de riesgo acumulado durante el primer año.
- **Variables que mueven el riesgo** del paciente, comparado con el paciente promedio del estudio.

## Cómo funciona

El tablero usa los dos modelos finales del reporte: una regresión logística para la mortalidad intrahospitalaria (AUC de 0.872 en prueba) y una regresión logística multinomial para la ventana temporal (AUC macro de 0.746). Sus coeficientes y parámetros de preprocesamiento (`modelo_tablero.json`) se exportaron desde el notebook del proyecto, y las predicciones se calculan en el navegador. Las probabilidades se corrigen por el efecto de la ponderación de clases para que reflejen la frecuencia real de cada desenlace.

Todo está en `index.html`; no requiere instalación ni servidor.

## Aviso

Herramienta académica. Los datos provienen de hospitales de Estados Unidos entre 1989 y 1994. No debe usarse para tomar decisiones clínicas.
