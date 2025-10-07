-- =========================================================
-- PROYECTO BASE DE DATOS RESTAURANTE
-- AUTORES: Jhon Sebastián y Jerónimo Quintero
-- GESTOR: MySQL
-- =========================================================

CREATE DATABASE IF NOT EXISTS restaurante;
USE restaurante;

-- =========================================================
-- 1. CREACIÓN DE TABLAS (DDL)
-- =========================================================

-- Tabla Clientes
CREATE TABLE Clientes (
    ID_cliente INT PRIMARY KEY,
    Nombre VARCHAR(50),
    Apellido VARCHAR(50),
    Telefono VARCHAR(15),
    Correo_electronico VARCHAR(100),
    Direccion VARCHAR(255)
);

-- Tabla Empleados
CREATE TABLE Empleados (
    ID_empleado INT PRIMARY KEY,
    Nombre VARCHAR(50),
    Apellido VARCHAR(50),
    Telefono VARCHAR(15),
    Correo_electronico VARCHAR(100),
    Puesto VARCHAR(50)
);

-- Tabla Platos
CREATE TABLE Platos (
    ID_plato INT PRIMARY KEY,
    Nombre VARCHAR(100),
    Descripcion VARCHAR(255),
    Precio DECIMAL(10, 2),
    Categoria VARCHAR(50)
);

-- Tabla Menus
CREATE TABLE Menus (
    ID_menu INT PRIMARY KEY,
    Nombre VARCHAR(100),
    Descripcion VARCHAR(255)
);

-- Tabla Platos_en_menu (relación N:M entre Platos y Menus)
CREATE TABLE Platos_en_menu (
    ID_plato_menu INT PRIMARY KEY,
    ID_plato INT,
    ID_menu INT,
    FOREIGN KEY (ID_plato) REFERENCES Platos(ID_plato),
    FOREIGN KEY (ID_menu) REFERENCES Menus(ID_menu)
);

-- Tabla Pedidos
CREATE TABLE Pedidos (
    ID_pedido INT PRIMARY KEY,
    ID_cliente INT,
    ID_empleado INT,
    Fecha DATE,
    Total DECIMAL(10, 2),
    FOREIGN KEY (ID_cliente) REFERENCES Clientes(ID_cliente),
    FOREIGN KEY (ID_empleado) REFERENCES Empleados(ID_empleado)
);

-- Tabla Detalles_pedido
CREATE TABLE Detalles_pedido (
    ID_detalle INT PRIMARY KEY,
    ID_pedido INT,
    ID_plato INT,
    Cantidad INT,
    Precio_unitario DECIMAL(10, 2),
    Subtotal DECIMAL(10, 2),
    FOREIGN KEY (ID_pedido) REFERENCES Pedidos(ID_pedido),
    FOREIGN KEY (ID_plato) REFERENCES Platos(ID_plato)
);

-- =========================================================
-- 2. INSERCIÓN DE DATOS (DML - CREATE)
-- =========================================================

-- Ejemplo de inserción Clientes (10 registros)
INSERT INTO Clientes VALUES
(1,'Ana','Torres','3124567890','ana@mail.com','Calle 10 #45-67'),
(2,'Luis','Martínez','3112345678','luis@mail.com','Cra 8 #12-45'),
(3,'Carlos','Pérez','3004567891','carlos@mail.com','Av 5 #23-90'),
(4,'María','Gómez','3123456789','maria@mail.com','Calle 20 #10-30'),
(5,'Sofía','Jiménez','3145678901','sofia@mail.com','Cra 15 #55-10'),
(6,'Pedro','Ramírez','3156789012','pedro@mail.com','Calle 7 #60-12'),
(7,'Laura','Sánchez','3101234567','laura@mail.com','Cra 25 #34-09'),
(8,'Andrés','Cano','3169876543','andres@mail.com','Av 33 #22-10'),
(9,'Camila','Rojas','3176549871','camila@mail.com','Calle 40 #50-25'),
(10,'Julio','Ospina','3198765432','julio@mail.com','Cra 9 #12-34');

-- Inserción de Empleados
INSERT INTO Empleados VALUES
(1,'Sara','Castaño','3109876543','sara@mail.com','Mesero'),
(2,'Juan','Vélez','3145671234','juan@mail.com','Cocinero'),
(3,'David','Gómez','3129087654','david@mail.com','Cajero'),
(4,'Marta','Ruiz','3112349087','marta@mail.com','Mesera'),
(5,'Nicolás','García','3104567890','nicolas@mail.com','Administrador'),
(6,'Lina','Morales','3156781234','lina@mail.com','Cocinera'),
(7,'Esteban','López','3167893456','esteban@mail.com','Mesero'),
(8,'Paula','Hernández','3176540987','paula@mail.com','Cocinera'),
(9,'Carlos','Arango','3196547890','carlos@mail.com','Mesero'),
(10,'Verónica','Díaz','3123456780','veronica@mail.com','Host');

-- Inserción de Platos
INSERT INTO Platos VALUES
(1,'Hamburguesa','Carne con queso y vegetales',15.99,'Rápida'),
(2,'Pizza Margarita','Queso mozzarella y tomate',14.50,'Italiana'),
(3,'Ensalada César','Lechuga, pollo y aderezo',12.00,'Saludable'),
(4,'Pasta Alfredo','Con crema y pollo',13.50,'Italiana'),
(5,'Taco Mexicano','Carne y salsa picante',9.99,'Mexicana'),
(6,'Pollo a la plancha','Con papas fritas',17.99,'Casera'),
(7,'Sopa de verduras','Con ingredientes frescos',8.50,'Vegetariana'),
(8,'Sushi','Rolls variados',11.99,'Japonesa'),
(9,'Empanadas','Rellenas de carne',10.50,'Colombiana'),
(10,'Arepa rellena','Queso y pollo',7.00,'Típica');

-- Inserción de Menus
INSERT INTO Menus VALUES
(1,'Menú Ejecutivo','Incluye plato fuerte y bebida'),
(2,'Menú Infantil','Porción pequeña y jugo'),
(3,'Menú Vegetariano','Platos sin carne ni pollo');

-- Inserción de Platos_en_menu
INSERT INTO Platos_en_menu VALUES
(1,1,1),(2,2,1),(3,3,1),(4,7,3),(5,10,2),(6,8,1);

-- Inserción de Pedidos
INSERT INTO Pedidos VALUES
(1,1,1,'2024-05-11',30.48),
(2,2,2,'2024-05-11',27.50),
(3,3,3,'2024-05-11',25.98),
(4,4,4,'2024-05-12',45.75),
(5,5,5,'2024-05-12',52.80),
(6,6,6,'2024-05-12',38.25),
(7,7,7,'2024-05-13',63.40),
(8,8,8,'2024-05-13',29.90),
(9,9,9,'2024-05-13',41.65),
(10,10,10,'2024-05-14',56.20);

-- Inserción de Detalles_pedido
INSERT INTO Detalles_pedido VALUES
(1,1,1,1,15.99,15.99),
(2,1,2,1,14.50,14.50),
(3,2,3,1,12.00,12.00),
(4,3,4,2,13.50,27.00),
(5,4,5,1,9.99,9.99),
(6,4,6,1,17.99,17.99),
(7,5,7,2,8.50,17.00),
(8,5,8,1,11.99,11.99),
(9,6,9,1,10.50,10.50),
(10,7,10,2,7.00,14.00);

-- =========================================================
-- 3. CREACIÓN DE ÍNDICES
-- =========================================================

CREATE INDEX idx_cliente ON Pedidos(ID_cliente);
CREATE INDEX idx_empleado ON Pedidos(ID_empleado);
CREATE INDEX idx_plato ON Detalles_pedido(ID_plato);

-- =========================================================
-- 4. CRUD COMPLETO (READ, UPDATE, DELETE)
-- =========================================================

-- SELECT (lectura básica)
SELECT * FROM Clientes;
SELECT * FROM Empleados;
SELECT * FROM Pedidos;

-- UPDATE ejemplos
UPDATE Clientes SET Telefono = '3156789123' WHERE ID_cliente = 3;
UPDATE Empleados SET Puesto = 'Administrador de turno' WHERE ID_empleado = 5;
UPDATE Platos SET Precio = 18.50 WHERE ID_plato = 7;
UPDATE Pedidos
SET Total = (SELECT SUM(Subtotal) FROM Detalles_pedido WHERE Detalles_pedido.ID_pedido = Pedidos.ID_pedido)
WHERE ID_pedido = 4;
UPDATE Platos SET Categoria = 'Promoción' WHERE ID_plato IN (10, 11, 12);

-- DELETE ejemplos
DELETE FROM Detalles_pedido WHERE ID_pedido = 8;
DELETE FROM Pedidos WHERE ID_pedido = 8;
DELETE FROM Clientes WHERE ID_cliente NOT IN (SELECT ID_cliente FROM Pedidos);
DELETE FROM Platos WHERE ID_plato NOT IN (SELECT ID_plato FROM Platos_en_menu);
DELETE FROM Empleados
WHERE ID_empleado NOT IN (
    SELECT DISTINCT ID_empleado FROM Pedidos
    WHERE Fecha >= DATE_SUB(CURDATE(), INTERVAL 3 MONTH)
);
DELETE FROM Detalles_pedido WHERE Subtotal = 0;

-- =========================================================
-- 5. CONSULTAS ANALÍTICAS Y VISTAS
-- =========================================================

-- Plato más vendido
SELECT p.Nombre AS Plato, COUNT(*) AS Ventas
FROM Detalles_pedido dp
JOIN Platos p ON dp.ID_plato = p.ID_plato
GROUP BY dp.ID_plato
ORDER BY Ventas DESC
LIMIT 1;

-- Total de ingresos por categoría
SELECT p.Categoria, SUM(dp.Cantidad * dp.Precio_unitario) AS Ingresos
FROM Detalles_pedido dp
JOIN Platos p ON dp.ID_plato = p.ID_plato
JOIN Pedidos pe ON dp.ID_pedido = pe.ID_pedido
GROUP BY p.Categoria;

-- Día con más ventas
SELECT DAYNAME(Fecha) AS Dia_semana, COUNT(*) AS Ventas
FROM Pedidos
GROUP BY Dia_semana
ORDER BY Ventas DESC
LIMIT 1;

-- Menú con mayores ingresos
SELECT m.Nombre AS Menu, SUM(dp.Subtotal) AS Ingresos_generados
FROM Detalles_pedido dp
JOIN Pedidos pe ON dp.ID_pedido = pe.ID_pedido
JOIN Platos_en_menu pm ON dp.ID_plato = pm.ID_plato
JOIN Menus m ON pm.ID_menu = m.ID_menu
GROUP BY m.Nombre
ORDER BY Ingresos_generados DESC
LIMIT 1;

-- Pedidos por empleado (último mes)
SELECT e.Nombre, COUNT(*) AS Pedidos_atendidos
FROM Pedidos pe
JOIN Empleados e ON pe.ID_empleado = e.ID_empleado
WHERE pe.Fecha >= DATE_SUB(CURDATE(), INTERVAL 1 MONTH)
GROUP BY e.Nombre;

-- Empleado con mayor gasto promedio
SELECT e.Nombre, AVG(dp.Subtotal) AS Gasto_promedio
FROM Detalles_pedido dp
JOIN Pedidos pe ON dp.ID_pedido = pe.ID_pedido
JOIN Empleados e ON pe.ID_empleado = e.ID_empleado
GROUP BY e.Nombre
ORDER BY Gasto_promedio DESC
LIMIT 1;

-- Clientes vegetarianos del último mes
SELECT COUNT(DISTINCT pe.ID_cliente) AS Clientes_vegetarianos
FROM Detalles_pedido dp
JOIN Platos p ON dp.ID_plato = p.ID_plato
JOIN Pedidos pe ON dp.ID_pedido = pe.ID_pedido
WHERE p.Categoria = 'Vegetariana'
AND pe.Fecha >= DATE_SUB(CURDATE(), INTERVAL 1 MONTH);

