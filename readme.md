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
    ('Empresa2', FALSE, 0, '2025-01-12'),
    ('Empresa3', TRUE, 3, '2025-01-01'),
    ('Empresa4', TRUE, 10, '2025-01-14'),
    ('Empresa5', TRUE, 7, '2025-01-20');
```
![imagen](https://github.com/user-attachments/assets/65753f8e-9eac-4b28-91df-c8bd106934f2)


Apartado 3
```sql
SELECT *
FROM EmpresasFCT
ORDER BY fechaContacto DESC;
```
![imagen](https://github.com/user-attachments/assets/97b72071-e4c8-4e2e-8bbf-233c24217dda)

Apartado 4
```sql
SELECT 
    contacto.name, 
    empresa.name
FROM 
    res_partner contacto
LEFT JOIN 
    res_partner empresa ON contacto.parent_id = empresa.id
WHERE 
    contacto.is_company = FALSE
    AND contacto.city = 'Tracy'
ORDER BY 
    empresa.name ASC;
```
![imagen](https://github.com/user-attachments/assets/9c168d5d-1231-4f2f-92fd-3fae18ae1dce)

Apartado 5
```sql
SELECT 
    partner.name, 
    move.name, 
    move.invoice_date, 
    move.amount_untaxed
FROM 
    account_move move
JOIN 
    res_partner partner ON move.partner_id = partner.id
WHERE 
    move.move_type = 'in_refund'
ORDER BY 
    move.invoice_date DESC;
```
![imagen](https://github.com/user-attachments/assets/f8d8e470-7be1-41e5-b3d5-0ce397275f97)

Apartado 6
```sql
SELECT 
    partner.name, 
    COUNT(move.id), 
    SUM(move.amount_untaxed)
FROM 
    account_move move
JOIN 
    res_partner partner ON move.partner_id = partner.id
WHERE 
    move.move_type = 'out_invoice'
    AND move.state = 'posted'
GROUP BY 
    partner.name
HAVING 
    COUNT(move.id) > 2;
```
![imagen](https://github.com/user-attachments/assets/89b48b18-4dae-4bf5-999d-0eebc9d351b3)

Apartado 7
```sql
UPDATE res_partner
SET email = REPLACE(email, '@bilbao.example.com', '@bilbao.bizkaia.neus')
WHERE email LIKE '%@bilbao.example.com';
```
![imagen](https://github.com/user-attachments/assets/cde37972-16b3-41e0-a086-63055ba68c84)

Apartado 8
```sql
DELETE FROM res_partner 
WHERE parent_id = (SELECT id FROM res_partner WHERE name = 'Ready Mat');
```
![imagen](https://github.com/user-attachments/assets/dbf03f2a-3953-4e07-ae17-1238950ff641)

![imagen](https://github.com/user-attachments/assets/5c029d12-d7de-4c22-9df2-fd3a84cfeb51)

![imagen](https://github.com/user-attachments/assets/a0543d9b-863b-4914-846c-3c4a21dd1e0e)

