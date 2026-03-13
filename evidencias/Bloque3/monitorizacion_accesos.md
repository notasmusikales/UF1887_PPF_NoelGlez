# BLOQUE 3 – MONITORIZACIÓN DE ACCESOS
## Objetivo
Analizar los registros del sistema para detectar accesos fallidos, sesiones activas y posibles intentos de intrusión.
---
## 1. Análisis de logs del sistema
Se revisaron los logs de autenticación del sistema Linux.
Archivo analizado:
/var/log/auth.log
Comando utilizado:
sudo tail -n 50 /var/log/auth.log
También se filtraron intentos fallidos de autenticación.
grep "Failed password" /var/log/auth.log
Se observaron algunos intentos fallidos de acceso con usuarios inexistentes.
---
## 2. Análisis de logs del ERP
Se revisaron los logs del contenedor de Odoo.
Comando utilizado:
docker logs odoo18 --tail 100
Se identificaron algunos intentos de acceso con credenciales incorrectas.
---
## 3. Análisis de sesiones activas
Se revisaron las sesiones activas en el sistema.
Comandos utilizados:
who
w
También se analizaron las conexiones activas a PostgreSQL.
Consulta utilizada:
SELECT usename, client_addr, state
FROM pg_stat_activity;
---
## 4. Posibles accesos sospechosos
Durante el análisis se detectaron posibles riesgos:
- intentos repetidos de acceso fallido
- accesos desde direcciones IP desconocidas
- usuarios inexistentes intentando autenticarse
Estos eventos pueden indicar intentos de intrusión o errores de autenticación.
---
## 5. Medidas de prevención
Para mejorar la seguridad del sistema se proponen las siguientes medidas:
- implementar fail2ban para bloquear intentos repetidos
- limitar accesos SSH
- utilizar HTTPS en el acceso al ERP
- revisar logs periódicamente
- aplicar contraseñas seguras
- desactivar cuentas inactivas
---
## 6. Conclusión
La monitorización de accesos permite detectar comportamientos anómalos en el sistema y aplicar medidas preventivas para evitar accesos no autorizados.