# 🛒 Market Basket Analysis & E-Commerce Analytics (Snowflake + Power BI)

> **Proyecto End-to-End de Analytics Engineering & Business Intelligence**  
> Implementación de Arquitectura Medallón en la nube (**Snowflake**), modelado relacional y desarrollo de un Dashboard ejecutivo e interactivo en **Power BI**.

---

## 📌 Introducción y Objetivo del Proyecto

El objetivo principal de este proyecto es analizar el comportamiento de compra de los clientes de un e-commerce a través de un análisis de la cesta de compras (**Market Basket Analysis**), identificando patrones de asociación entre productos, frecuencia de compra y métricas clave de facturación (*Sales Analytics*).

Para garantizar la calidad, escalabilidad y trazabilidad de los datos, la solución fue construida integrando:
- **VS Code**: Desarrollo y control de versión de scripts SQL.
- **Snowflake (Data Cloud)**: Almacenamiento, transformación e ingesta bajo Arquitectura Medallón.
- **Power BI**: Modelado dimensional, cálculo de métricas avanzadas en DAX y visualización ejecutiva.

---

## 🏗️ Arquitectura de la Solución (Arquitectura Medallón)

La ingesta y transformación de datos dentro de Snowflake se estructuró en tres capas analíticas:

+-----------------------------------------------------------------------+
|                         FUENTES DE DATOS (CSV)                        |
+-----------------------------------------------------------------------+
|
v
+-----------------------------------------------------------------------+
| 🥉 CAPA BRONZE (Staging Layer)                                        |
| Ingesta directa de datos crudos desde stage sin alteraciones.         |
+-----------------------------------------------------------------------+
|
v
+-----------------------------------------------------------------------+
| 🥈 CAPA SILVER (Analytics / Refined Layer)                            |
| Limpieza de nulos, casteo de tipos de datos, estandarización de      |
| fechas y eliminación de duplicados.                                   |
+-----------------------------------------------------------------------+
|
v
+-----------------------------------------------------------------------+
| 🥇 CAPA GOLD (Data Marts / Business Layer)                            |
| Modelado final, tablas de hechos (FACT_VENTAS) y agregaciones       |
| preparadas para el consumo en Power BI.                               |
+-----------------------------------------------------------------------+


---

## 📐 Modelo de Datos y Tablas en Power BI

El modelo de datos se diseñó bajo una estructura optimizada para análisis de asociación y dimensiones temporales:

* **`FACT_VENTAS`** *(Tabla de Hechos)*: Centraliza las transacciones con métricas de órdenes, productos, usuarios, recompra e ingresos.
* **`FACT_VENTAS_ESPEJO`**: Tabla de hechos autocruzada para calcular las combinaciones del Market Basket Analysis (soporte, confianza y lift).
* **`CALENDARIO`**: Dimensión de fechas autogenerada para filtrado analítico (Año, Mes, Día de la Semana).
* **`DIM_DIAS`**: Dimensión auxiliar para categorización e identificación de días.
* **`MEDIDAS`**: Tabla dedicada a albergar la lógica DAX del modelo (`% Confianza Combo`, `Lift Categoria`, `Lift_Combo_Fijo`, `Tasa_Recompra`, `Dias_Promedio_Entre_Compras`, entre otras).

---

## 🛠️ Tecnologías y Herramientas Utilizadas

* **Snowflake**: Almacenamiento y procesamiento SQL en la nube.
* **SQL (ANSI & Snowflake Dialect)**: Desarrollo de Vistas, CTEs, Funciones de Ventana y DDL/DML.
* **Power BI Desktop**: Conexión e ingesta, modelo de datos relacional, expresiones **DAX** y diseño UI/UX del reporte.
* **Visual Studio Code**: Entorno de desarrollo para scripting SQL y gestión del proyecto.

---

## 📈 Visualización y Resultados en Power BI

El Dashboard interactivo desarrollado en Power BI permite explorar:
1. **Métricas Principales (KPIs)**: Total Facturado, Ticket Promedio, Tasa de Recompra y Días Promedio entre compras.
2. **Market Basket Analysis**: Análisis de reglas de asociación entre productos (*Support*, *Confidence* y *Lift*) para estrategias de *cross-selling*.
3. **Análisis Temporal**: Evolución de ventas y estacionalidad a través de la dimensión calendario.

---

## 📁 Estructura del Repositorio

├── 01_snowflake_scripts/
│   ├── 1_Capa_Bronze.sql
│   ├── 2_Capa_Silver.sql
│   └── 3_Capa_Gold.sql
├── 02_powerbi_multimedia/
│   └── Market_Basket_Analysis.pbix
└── README.md


---
*Desarrollado como parte del portfolio profesional de Business Intelligence & Data Analytics.*

















