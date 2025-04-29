# Análisis de la Brecha Digital en Uruguay: Perfiles de Conectividad y Factores Asociados (Censo 2023)

## Introducción

Este proyecto utiliza los microdatos del Censo de Población, Hogares y Viviendas de Uruguay 2023 para realizar un análisis de la brecha digital en el país. La brecha digital, entendida como las desigualdades en el acceso y uso de las Tecnologías de la Información y Comunicación (TIC), es un factor clave para el desarrollo social y económico. Comprender su magnitud, distribución geográfica y los factores asociados es fundamental para el diseño de políticas públicas efectivas.

El análisis se estructura en dos fases principales, combinando técnicas de aprendizaje no supervisado y supervisado para obtener una visión completa del fenómeno.

## Objetivos Generales

1.  **Identificar y caracterizar** diferentes perfiles o tipologías de hogares en Uruguay según su nivel y tipo de acceso a recursos digitales clave (internet y dispositivos).
2.  **Analizar la distribución geográfica** de estos perfiles de conectividad para visualizar las desigualdades territoriales.
3.  **Determinar los factores socioeconómicos, demográficos y de infraestructura** más relevantes que explican las diferencias en el acceso digital entre los hogares dentro de cada perfil identificado.

## Objetivos Específicos

**Fase 1: Identificación y Mapeo de Perfiles de Conectividad (Análisis No Supervisado)**

*   Aplicar algoritmos de clustering (Kmeans) sobre variables seleccionadas de hogares, viviendas y características del jefe/a de hogar para agrupar hogares con patrones similares de acceso a internet (`HOGCE11`), posesión de dispositivos (`HOGCE28`) y contexto clave (electricidad, educación del jefe, etc.).
*   Describir cada cluster resultante (perfil de hogar) en términos de sus características promedio de conectividad, socioeconómicas, demográficas y de vivienda.

**Fase 2: Análisis de Factores Relevantes por Perfil (Análisis Supervisado / Descriptivo)**

*   Para los perfiles identificados en la Fase 1 con menor conectividad:
    *   Construir modelos de clasificación para predecir la pertenencia a ese cluster vs otros, identificando los predictores más importantes.
    *   Realizar un análisis descriptivo comparando las características (educación, ocupación, tipo de hogar, etc.) de los hogares dentro de ese cluster con el promedio nacional o con otros clusters, para resaltar los factores diferenciales clave.
*   Interpretar los resultados para entender qué variables tienen mayor impacto en la probabilidad de que un hogar pertenezca a un perfil de baja conectividad, una vez considerado el contexto general definido por el cluster.

## Fuentes de Datos

*   Microdatos del Censo de Población, Hogares y Viviendas 2023 ([INE Uruguay](https://www.gub.uy/instituto-nacional-estadistica/politicas-y-gestion/microdatos-censo-2023-anonimizados)).
    *   [Dataset de Hogares](https://www5.ine.gub.uy/documents/CENSO%202023/Microdatos/hogares_ext_26_02.rar).
    *   [Dataset de Viviendas](https://www5.ine.gub.uy/documents/CENSO%202023/Microdatos/viviendas_ext_26_02.rar).
    *   [Dataset de Personas](https://www5.ine.gub.uy/documents/CENSO%202023/Microdatos/personas_ext_26_02.rar).
*   Documentación asociada a los microdatos ([Diccionarios de Variables](https://www5.ine.gub.uy/documents/CENSO%202023/Microdatos/Diccionario%20de%20variables%202023.xlsx)).

## Metodología Propuesta

1.  **Preprocesamiento:** Carga, limpieza, manejo de valores faltantes, filtrado por sub-universo relevante (hogares particulares ocupados), unión de los datasets.
2.  **Ingeniería de Características:** Creación de variables derivadas. Codificación de variables categóricas y escalado de numéricas según sea necesario para los algoritmos.
3.  **Fase 1 - Clustering:** Aplicación de Kmeans, selección del número óptimo de clusters, asignación de etiquetas de cluster.
4.  **Fase 2 - Análisis por Cluster:** Construcción y evaluación de modelos predictivos (o análisis descriptivo comparativo) para el cluster de interés. Interpretación de la importancia de variables.
5.  **Conclusiones:** Síntesis de los hallazgos sobre los perfiles de conectividad, su distribución y los factores asociados a la brecha digital.

## Resultados Esperados

*   Una tipología clara de hogares uruguayos basada en su perfil de conectividad digital.
*   Identificación y cuantificación de los factores (educativos, económicos, geográficos, de infraestructura) más determinantes de la exclusión digital, con especificidades según el perfil del hogar.
*   Insights relevantes para informar políticas públicas orientadas a reducir la brecha digital en Uruguay.
