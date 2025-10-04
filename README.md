Base de Datos SQL – Restaurante

Introducción

Este proyecto presenta el diseño de una base de datos orientada a la gestión de la información de un restaurante, abarcando datos sobre clientes, pedidos, productos, menús y empleados.

El propósito principal es facilitar la obtención de información relevante para la toma de decisiones mediante la ejecución de diversas consultas SQL.

Estructura de la Base de Datos

El modelo de datos está conformado por las siguientes entidades y relaciones:

Clientes: Contiene los datos personales de los clientes del restaurante.

Empleados: Registra la información del personal que atiende los pedidos.

Pedidos: Almacena los pedidos realizados por los clientes.

Productos: Incluye la descripción y el precio de los platos, bebidas y demás artículos ofrecidos.

Menús: Define los menús disponibles en el restaurante.

Composición del Menú: Relaciona los productos incluidos dentro de cada menú.

Detalles del Pedido: Indica qué productos conforman cada pedido y sus respectivas cantidades.

Reglas y Restricciones del Modelo

Cada cliente y empleado posee un identificador único (ID).

Todo pedido está asociado a un cliente y a un empleado.

Cada producto cuenta con un precio definido.

Los menús agrupan múltiples productos, especificando las cantidades.

Los detalles de pedido reflejan los productos solicitados por cada cliente y sus cantidades.

Etapas de Desarrollo del Proyecto
1. Boceto Inicial

En esta fase se elabora un primer esquema conceptual con las tablas necesarias para gestionar la información del restaurante.

2. Diagrama de Tablas (Modelo E/R)

A continuación, se representa el diseño de la base de datos en un diagrama entidad-relación que muestra cómo interactúan las tablas entre sí.

3. Creación de la Base de Datos y Carga de Datos

Mediante código SQL se construye la estructura de la base de datos y sus respectivas tablas.
La carga de información se realiza de forma manual para las tablas Clientes, Pedidos, Empleados, Platos y Menús, mientras que las tablas Detalles_Pedido y Platos_en_Menu se completan a través de archivos externos.

4. Consultas SQL
4.1 Análisis de Ventas

Día con mayor número de ventas.

Plato más solicitado del restaurante.

Menú con mayores ingresos durante el último año.

Total de ingresos por categoría de plato en el último mes.

4.2 Desempeño del Personal

Empleado con clientes de mayor gasto promedio.

Empleado que generó más ingresos en el último trimestre.

Número de pedidos atendidos por cada empleado en el último mes.

4.3 Preferencias de los Clientes

Número de clientes que solicitaron platos vegetarianos durante el último mes.

Platos más populares entre los clientes frecuentes.

Si deseas consultar las queries completas, puedes acceder a ellas en el archivo correspondiente dentro del repositorio.
