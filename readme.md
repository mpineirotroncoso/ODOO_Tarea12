# Tarea 12
Apartado 1
```sql
CREATE TABLE EmpresasFCT (
    idEmpresa SERIAL PRIMARY KEY,
    nombre VARCHAR(40) NOT NULL,
    quiereAlumnos BOOLEAN,
    numAlumnos INTEGER,
    fechaContacto DATE
);
```
![imagen](https://github.com/user-attachments/assets/c0da5b38-422a-478d-92df-62e148aaf872)

Apartado 2
```sql
INSERT INTO EmpresasFCT (nombre, quiereAlumnos, numAlumnos, fechaContacto)
VALUES
    ('Empresa1', TRUE, 5, '2025-01-25'),
    ('Empresa1', FALSE, 0, '2025-01-12'),
    ('Empresa1', TRUE, 3, '2025-01-01'),
    ('Empresa1', TRUE, 10, '2025-01-14'),
    ('Empresa1', TRUE, 7, '2025-01-20');
```
![imagen](https://github.com/user-attachments/assets/325673bd-a3dc-4ad8-b96d-e4fd28f1b09c)
