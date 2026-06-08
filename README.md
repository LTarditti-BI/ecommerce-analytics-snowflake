# ecommerce-analytics-snowflake
Estructuración analítica y modelado de datos en Snowflake para BI Comercial.
## Introducción del Proyecto
Este es mi primer proyecto oficial de **Business Intelligence** en la nube usando *Snowflake*.

## 🏗️ Arquitectura de la Solución (Arquitectura Medallón)
El proyecto está estructurado en tres capas dentro de Snowflake para garantizar la limpieza y calidad de los datos.
 **Capa Bronze (Staging)**: Ingesta de los datos puros del e-commerce tal cual vienen del sistema origen. 
 **Capa Silver (Analytics)**: Limpieza de datos, manejo de nulos, formateo de fechas y validación de tipos de datos. **Capa Gold (Data Marts)**: Tablas agregadas y optimizadas listas para el consumo de negocio y tableros de BI.
## 📁 Diccionario de Datos y Tablas Principales
A continuación se detallan las estructuras de las tablas clave que componen el modelo analítico:
## 1. Tabla: stg_orders (Capa Bronze)
Esta tabla contiene el histórico de órdenes de compra del e-commerce. 

| Campo | Tipo de Datos | Descripción |
| :--- | :--- | ---: |
| order_id | VARCHAR | Identificador único de la orden | 
| customer_id | VARCHAR | Código de identificación del cliente |
| order_date | TIMESTAMP |Fecha y hora en la que se realizó la compra |
| total_amount | NUMBER | Monto total facturado |
 ## 2. Tabla: nombre_tabla (Capa Silver)
 Breve descripción de qué datos tiene esta tabla.

 | Columna | Tipo de Datos | Descripción |
 | :--- | :--- | ---: |
 | campo_1 | VARCHAR | Explicación de qué es |
 | campo_2 | NUMBER | Explicación de qué es |














