1. Título del Proyecto 
Pronóstico de Ocupación de Camas UCI: Un Método para la Optimización del Personal de Enfermería utilizando herramientas de machine learning

2. Resumen Ejecutivo (Project Overview)
Este proyecto aborda el desafío administrativo crítico de la gestión de recursos de los servicios hospitalarios (UCI para el presente caso) mediante la implementación de un modelo de series de tiempo para el pronóstico de la Ocupación Diaria de Camas. El enfoque está en capturar la inercia sistémica del flujo de pacientes (Duración de la Estancia - LOS) y el impacto en el proceso de atención del ciclo semanal. El pronóstico entrega a la gerencia hospitalaria datos procesables para la planificación de capacidad, permitiendo el ajuste proactivo de turnos de enfermería con hasta 14 días de anticipación, lo que reduce significativamente los costos asociados a las horas extras y la contratación de personal de agencia de última hora.

3. Metodología y Rigor Estadístico
3.1 Métrica Central: Cálculo de la Ocupación Diaria
La métrica principal es la Ocupación Diaria de Pacientes, que es superior al simple conteo de ingresos ya que considera la inercia generada por la Duración de la Estancia (LOS). La transformación de los datos transaccionales (intime/outtime) en una serie de tiempo continua se realiza en Pandas mediante el cálculo de la diferencia acumulada entre las admisiones y las altas (técnica vectorizada cumsum()).

3.2 La Limitación Temporal de MIMIC-IV (La Crítica Esencial)
Nota Metodológica Crítica: Debido al desplazamiento de fecha aleatorio aplicado a cada paciente en MIMIC-IV para la deidentificación, el alcance de la predicción está metodológicamente limitado a la dinámica operacional interna del hospital. El modelo no tiene valor predictivo para la estacionalidad anual o eventos epidemiológicos externos.

Patrones Preservados: La predicción se basa en la Autocorrelación (la dependencia secuencial de la ocupación) y la Estacionalidad Semanal (el patrón conservado del Día de la Semana).

Alcance: El valor del modelo reside en la gestión operativa de la capacidad a corto plazo (planificación semanal de turnos), demostrando la eficiencia del sistema ante sus propios ritmos internos.

4. Análisis de Datos (EDA) y Resultados del Modelo (Placeholder)
[Visual 1] Gráfico de la Serie de Tiempo de Ocupación Diaria completa (Muestra la inercia del sistema).

[Visual 2] Gráfico de caja (Boxplot) de la Ocupación por Día de la Semana (Demuestra la estacionalidad conservada).

Resultado Clave: (Pendiente) Indicar el modelo final (Prophet) y las métricas de rendimiento clave, como el Error Absoluto Medio (MAE) en camas (Ej: "MAE de 1.2 camas, lo que permite una planificación del personal con un margen de error mínimo").

5. Stack Técnico y Dependencias
Lenguaje: Python 🐍

Librerías Base: Pandas, NumPy, Matplotlib/Seaborn.

Modelo de Pronóstico: Prophet (o especificar ARIMA/SARIMA).

Fuente de Datos: MIMIC-IV v3.1 (icustays table).

6. Uso y Replicación
Instrucciones concisas para descargar los datos (icustays.csv.gz) y la ruta para ejecutar el notebook (src/forecasting_notebook.ipynb).