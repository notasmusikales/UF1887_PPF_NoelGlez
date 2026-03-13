# BLOQUE 4 – COPIA DE SEGURIDAD DEL SISTEMA
## Objetivo
- Realizar una copia de seguridad del sistema ERP-CRM que incluya la base de datos y los archivos del ERP, así como documentar el procedimiento de restauración.
---
## 1. Copia de seguridad de la base de datos
- Se utilizó la herramienta pg_dump de PostgreSQL para generar la copia.
Comando utilizado:
```
docker exec odoo18-db pg_dump -U odoo odoo18 > backup_odoo18.sql
```
- Este comando genera un archivo SQL que contiene toda la estructura y     datos de la base de datos.
Archivo generado:
``` 
backup_odoo18.sql
```
---
## 2. Copia de seguridad de archivos del ERP
- También se realizó copia de los archivos del ERP.
- Comando utilizado:
```
tar -czvf backup_odoo_files.tar.gz /opt/odoo
```
- Archivo generado:
```
backup_odoo_files.tar.gz
``` 
- Este archivo contiene el código del ERP y los módulos instalados.
---
## 3. Tipo de backup
#### Se realizó un backup completo del sistema.
Incluye:
- base de datos PostgreSQL
- archivos del ERP
Este tipo de copia permite recuperar completamente el sistema en caso de fallo.
---
## 4. Periodicidad recomendada
#### Para garantizar la seguridad de la información se recomienda:
- backup de base de datos diario
- backup de archivos semanal
- almacenamiento externo periódico
---
## 5. Procedimiento de restauración
#### Para restaurar la base de datos se utiliza:
```
psql -U odoo odoo18 < backup_odoo18.sql
```
#### Para restaurar los archivos del ERP:
```
tar -xzvf backup_odoo_files.tar.gz
```
- Finalmente se reinicia el ERP para aplicar los cambios.
---
## 6. Conclusión
Las copias de seguridad permiten proteger la información del sistema ERP-CRM y garantizar la recuperación del servicio en caso de fallos del sistema o pérdida de datos.