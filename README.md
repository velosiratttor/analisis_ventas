# 📊 Análisis de Ventas — Power BI

## 📌 Descripción del proyecto

Proyecto de análisis y visualización de datos desarrollado en **Microsoft Power BI**, orientado al análisis de ventas y al seguimiento de indicadores comerciales.

El proyecto parte de información de ventas que fue sometida a procesos de **limpieza, transformación y estructuración**, para posteriormente construir un modelo de datos que permitiera realizar análisis mediante medidas DAX y visualizaciones interactivas.

El objetivo principal fue construir un modelo que facilitara el análisis de las ventas desde diferentes perspectivas, como productos, vendedores, clientes y períodos de tiempo.

---

## 🎯 Objetivos

* Preparar y limpiar información de ventas.
* Transformar datos utilizando Power Query.
* Diseñar un modelo de datos estructurado.
* Construir un **modelo dimensional tipo estrella**.
* Crear relaciones entre tablas.
* Desarrollar medidas utilizando DAX.
* Construir indicadores comerciales.
* Analizar el comportamiento de las ventas.
* Crear dashboards interactivos para facilitar la interpretación de la información.

---

## 🛠️ Herramientas utilizadas

* **Microsoft Power BI**
* **Power Query**
* **DAX**
* **Power Pivot**
* **Excel**
* Modelo dimensional / Modelo estrella

---

## 🔄 Proceso de trabajo

El proyecto se desarrolló siguiendo un flujo similar al utilizado en procesos reales de análisis de datos:

```text
Datos originales
      ↓
Limpieza y transformación
      ↓
Preparación de tablas
      ↓
Modelado de datos
      ↓
Relaciones
      ↓
Medidas DAX
      ↓
Visualizaciones
      ↓
Dashboard
      ↓
Análisis
```

---

## 🧹 1. Limpieza y transformación de datos

Una de las primeras etapas consistió en preparar la información antes de utilizarla en el modelo.

Mediante **Power Query** se realizaron procesos de transformación y limpieza para obtener información más consistente y adecuada para el análisis.

Entre las tareas trabajadas se encuentran:

* Revisión de registros.
* Limpieza de datos.
* Tratamiento de valores nulos.
* Corrección y transformación de tipos de datos.
* Preparación de columnas.
* Eliminación de información innecesaria.
* Transformación de datos para su posterior modelado.
* Estructuración de las tablas utilizadas en el modelo.

El objetivo fue evitar llevar directamente al modelo datos sin preparar.

---

## 🏗️ 2. Modelado de datos

Después de preparar la información se construyó un **modelo dimensional basado en un esquema estrella**.

La tabla central del modelo es:

### `FactVentas`

Esta tabla contiene los registros relacionados con las operaciones de venta y funciona como tabla de hechos del modelo.

Alrededor de ella se encuentran las tablas utilizadas para proporcionar contexto al análisis.

El modelo permite analizar las ventas desde diferentes dimensiones, evitando mantener toda la información en una única tabla.

### Concepto utilizado

```text
              DimProducto
                   │
                   │
DimCliente ─── FactVentas ─── DimVendedor
                   │
                   │
                DimFecha
```

La estructura facilita realizar análisis por diferentes dimensiones sin duplicar innecesariamente información descriptiva.

---

## 🔗 3. Relaciones

Se configuraron relaciones entre la tabla de hechos y las tablas dimensionales.

La tabla `FactVentas` funciona como punto central del modelo y las dimensiones proporcionan el contexto necesario para analizar las operaciones.

Este enfoque permite realizar consultas como:

* ¿Cuánto se vendió?
* ¿Cuánto vendió cada vendedor?
* ¿Qué productos generan más ventas?
* ¿Cómo evolucionan las ventas por período?
* ¿Qué clientes generan mayor volumen de ventas?

---

## 🧮 4. Medidas DAX

Una parte importante del proyecto fue la creación de medidas mediante **DAX**.

Entre las medidas desarrolladas se encuentra:

```DAX
Total_Ventas =
SUMX(
    FactVentas,
    FactVentas[Precio] * FactVentas[Cantidad]
    - (FactVentas[Precio] - FactVentas[Descuento])
)
```

Estas medidas permiten realizar cálculos dinámicos sobre el modelo y utilizar los resultados en diferentes visualizaciones.

El uso de medidas permite que los indicadores respondan a los filtros y segmentaciones aplicados en el reporte.

---

## 📊 5. Dashboard y visualizaciones

A partir del modelo y las medidas DAX se construyeron diferentes páginas de análisis.

El reporte fue organizado para permitir una navegación más clara entre los diferentes aspectos de la información.

Entre los análisis desarrollados se incluyen:

### 📈 Análisis general

Página destinada a presentar una visión general del comportamiento de las ventas mediante indicadores y visualizaciones.

Permite obtener rápidamente una perspectiva del desempeño comercial.

### 🛒 Análisis de ventas

Se utilizaron visualizaciones para analizar el comportamiento de las operaciones y facilitar la identificación de tendencias y diferencias entre los datos.

### 👥 Análisis de vendedores

Se desarrolló una página específica para analizar el desempeño de los vendedores.

Esta página permite comparar vendedores y observar su participación dentro de las ventas.

El objetivo es facilitar preguntas como:

* ¿Qué vendedores generan mayores ventas?
* ¿Cómo se distribuyen las ventas entre vendedores?
* ¿Qué vendedores presentan mayor participación?
* ¿Cómo cambia el desempeño al aplicar diferentes filtros?

---

## 🎛️ 6. Interactividad

El reporte incorpora elementos interactivos de Power BI para permitir que el usuario explore la información.

Se trabajó con:

* Segmentadores.
* Filtros.
* Gráficos interactivos.
* Tarjetas de indicadores.
* Tablas y matrices.
* Cruce de información entre visualizaciones.

La interacción entre estos elementos permite analizar los datos desde diferentes perspectivas sin modificar el modelo.

---

## 📐 7. Enfoque de modelado

Uno de los principales aprendizajes del proyecto fue comprender que un buen reporte de Power BI no depende únicamente de crear gráficos.

El proceso comienza con:

**Datos → Transformación → Modelo → Relaciones → DAX → Visualización**

El modelo estrella permite separar:

* **Hechos:** información cuantitativa relacionada con las ventas.
* **Dimensiones:** información descriptiva utilizada para analizar esos hechos.

Esto facilita la creación de medidas y mejora la organización del modelo.

---

## 🧠 Conocimientos aplicados

Durante el desarrollo del proyecto se aplicaron conocimientos relacionados con:

### Power Query

* Importación de datos.
* Limpieza.
* Transformación.
* Preparación de información.
* Tratamiento de registros inconsistentes.

### Modelado

* Modelo estrella.
* Tablas de hechos.
* Tablas de dimensiones.
* Relaciones.
* Claves.
* Cardinalidad.

### DAX

* Creación de medidas.
* Cálculos sobre tablas.
* Uso de `SUMX`.
* Indicadores dinámicos.
* Integración de medidas con visualizaciones.

### Power BI

* Diseño de dashboards.
* Segmentadores.
* Filtros.
* Visualizaciones.
* Navegación entre páginas.
* Análisis interactivo.

---

## 📁 Estructura del repositorio

```text
PowerBI-Analisis-Ventas/
│
├── README.md
│
├── datos/
│   └── datos_ventas.xlsx
│
├── powerbi/
│   └── analisis_ventas.pbix
│
└── capturas/
    ├── dashboard_general.png
    ├── analisis_ventas.png
    └── vendedores.png
```

> Los nombres de archivos pueden variar dependiendo de la estructura utilizada en el proyecto.

---

## 📷 Capturas del proyecto

### Dashboard general

```markdown
![Dashboard general](capturas/dashboard_general.png)
```

### Análisis de ventas

```markdown
![Análisis de ventas](capturas/analisis_ventas.png)
```

### Página de vendedores

```markdown
![Análisis de vendedores](capturas/vendedores.png)
```

---

## 🚀 Resultado

El proyecto permitió construir un flujo completo de análisis utilizando Power BI, comenzando desde la preparación de los datos hasta la creación de un reporte interactivo.

El resultado integra:

* Limpieza y transformación de datos.
* Modelado dimensional.
* Modelo estrella.
* Relaciones entre tablas.
* Medidas DAX.
* KPIs.
* Visualizaciones interactivas.
* Análisis de ventas.
* Análisis por vendedores.

Más que enfocarse únicamente en la visualización, el proyecto busca demostrar el proceso completo de **preparación, modelado y análisis de datos**.

---

## 👨‍💻 Autor

**José Martín Pereira Hernández**

Ingeniero en Computación | Analista de Datos

**Tecnologías principales:**
Power BI · Power Query · Power Pivot · DAX · Excel · SQL · Python

---

## 📌 Nota

Este proyecto fue desarrollado con fines de aprendizaje y construcción de portafolio profesional, aplicando conceptos de análisis y modelado de datos con Power BI.
