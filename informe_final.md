# INFORME FINAL – SEGURIDAD DEL SISTEMA ERP
## 1. Introducción
#### El presente informe documenta el análisis de seguridad realizado sobre el sistema ERP, así como las medidas aplicadas para mejorar el control de accesos, la monitorización del sistema y la gestión de copias de seguridad.
---
## 2. Análisis inicial
Se realizó una revisión del sistema para identificar posibles riesgos de seguridad.
Se analizaron:
- usuarios existentes
- roles configurados
- permisos asignados
- accesos a módulos del ERP
Durante el análisis se detectaron algunos accesos innecesarios a módulos sensibles y la necesidad de mejorar la estructura de permisos.
---
## 3. Medidas aplicadas
Para mejorar la seguridad del sistema se aplicaron las siguientes medidas:
- corrección de permisos incorrectos
- creación de perfiles de seguridad
- restricción de accesos a módulos sensibles
Estas acciones permiten controlar de forma más precisa el acceso de los usuarios al sistema.
---
## 4. Monitorización de accesos
Se analizaron los logs del sistema para identificar posibles intentos de acceso no autorizados.
Se revisaron:
- logs del sistema
- logs del ERP
- sesiones activas
- intentos fallidos de autenticación
---
## 5. Copias de seguridad
Se implementó un sistema de backup que incluye:
- copia de seguridad de la base de datos
- copia de archivos del ERP
Estas copias permiten recuperar el sistema en caso de fallo o pérdida de datos.
---
## 6. Restauración del sistema
Se realizó una simulación de restauración utilizando las copias generadas.
Tras la restauración se verificó:
- funcionamiento del ERP
- integridad de los datos
- acceso correcto de los usuarios
Los resultados confirmaron que el sistema puede recuperarse correctamente.
---
## 7. Conclusión
Las medidas aplicadas mejoran la seguridad del sistema ERP, reduciendo riesgos de accesos indebidos y garantizando la recuperación del sistema en caso de incidente.
---
## 8. Recomendaciones
Para mantener la seguridad del sistema se recomienda:
- revisar periódicamente los usuarios y permisos
- monitorizar los logs del sistema
- realizar copias de seguridad periódicas
- mantener el sistema actualizado