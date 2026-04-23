# 🫁 Atenciones de Urgencia por Enfermedades Respiratorias — Región del Biobío

> Dashboard interactivo en Power BI que analiza las atenciones de urgencia por causas respiratorias en establecimientos de salud de la Región del Biobío entre 2019 y 2026.

\---

## 📌 Descripción del Proyecto

Este proyecto presenta un análisis visual de los registros de atenciones de urgencia clasificadas por causas respiratorias en la Región del Biobío. El dashboard fue desarrollado para la **Unidad de Bioestadística del Depto. de Salud Pública y Planificación Sanitaria — SEREMI Región del Biobío**, con última actualización al 10 de febrero de 2026.

El modelo de datos fue construido desde cero integrando tablas de hechos anuales (2019–2026) con dimensiones de establecimientos, causas de atención y semana epidemiológica, resolviendo la ausencia de información de servicio de salud en los registros históricos (2019–2022) mediante una relación indirecta a través de la comuna y el establecimiento.

\---

## 🖼️ Vista Previa del Dashboard

### Portada

!\[Portada](images/01\_portada.png)

### Total Atenciones por Causas Respiratorias

!\[Total Causas Respiratorias](images/02\_total\_causas\_respiratorias.png)

### Proporción de Hospitalizaciones

!\[Tasa de Hospitalizaciones](images/03\_tasa\_hospitalizaciones.png)

### Comparación por Servicio de Salud

!\[Comparación por Servicio de Salud](images/04\_comparacion\_servicio\_salud.png)

### Comparación por Rango de Edad

!\[Comparación por Rango de Edad](images/05\_comparacion\_rango\_edad.png)

\---

## 📊 Páginas del Dashboard

|Página|Descripción|
|-|-|
|**Portada**|Presentación del reporte con navegación principal|
|**Total Causas Respiratorias**|Atenciones y hospitalizaciones por semana epidemiológica y causa, con tabla de detalle|
|**Tasa de Hospitalizaciones**|Proporción de hospitalizaciones derivadas de urgencias respiratorias por semana y año|
|**Comparación por Servicio de Salud**|Atenciones y hospitalizaciones desagregadas por SS Arauco, Biobío, Concepción y Talcahuano|
|**Comparación por Rango de Edad**|Atenciones y hospitalizaciones por tramo etario (0–1, 1–4, 5–14, 15–64, 65 y más)|

\---

## 🔎 Filtros Disponibles

|Filtro|Opciones|
|-|-|
|Servicio de Salud|Arauco, Biobío, Concepción, Talcahuano|
|Tipo de Establecimiento|Hospital, SAPU, SAPUS, SURT|
|Causa de Atención|Bronquitis, Covid-19, Influenza, IRA Alta, Neumonía, entre otras|
|Causa de Hospitalización|Covid-19 identificado, Covid-19 no identificado, Sistema respiratorio|
|Comuna|Todas las comunas de la Región del Biobío|
|Año|2019 – 2026|

\---

\---

## 🧩 Modelo de Datos

El modelo sigue una arquitectura tipo **estrella/copo de nieve**, con las siguientes tablas:

**Tablas de hechos (7 tablas anuales):**

* `AtencionedeUrgencia2019` → `AtencionedeUrgencia2025`
* Contienen métricas de atención por rango etario, fecha, causa y establecimiento

**Tablas de dimensión:**

* `Establecimientos` — Nombre oficial, comuna, región, código de dependencia jerárquica
* `ID Causa` — Glosa y código de causa de atención
* `Semana Epidemiológica` — Año epidemiológico, fecha y número de semana

> \*\*Nota metodológica:\*\* Las tablas de hechos del período 2019–2022 no incluían información directa de servicio de salud. Esta limitación fue resuelta mediante una relación entre la tabla de Establecimientos y las tablas de hechos a través del código de establecimiento, permitiendo inferir el servicio de salud correspondiente a partir de la comuna de cada establecimiento.

\---

## 🛠️ Herramientas Utilizadas

* **Power BI Desktop** — Modelo de datos, medidas DAX y visualizaciones
* **Excel / CSV** — Fuente de datos original (DEIS, Ministerio de Salud de Chile)

\---

## 📁 Fuente de Datos

Los datos provienen del **Departamento de Estadísticas e Información de Salud (DEIS)** del Ministerio de Salud de Chile, disponibles públicamente en:
🔗 [https://deis.minsal.cl](https://deis.minsal.cl)

\---

