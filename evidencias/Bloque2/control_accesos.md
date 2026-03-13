# BLOQUE 2 – CONTROL DE ACCESOS
## Objetivo
- Aplicar medidas de seguridad sobre el sistema ERP mediante la modificación de
permisos incorrectos, creación de perfiles de seguridad y limitación de
accesos a módulos sensibles.
---
## 1. Modificación de permisos incorrectos
Se revisaron los usuarios existentes y se detectaron permisos excesivos.
### Correcciones aplicadas
| Usuario | Problema detectado | Acción aplicada |
|-------|------------------|----------------|
| comercial1 | Acceso a ajustes del sistema | Eliminado permiso de administración |
| soporte1 | Acceso a contabilidad | Eliminado acceso al módulo contable |
| admin | Uso general del sistema | Recomendación de uso exclusivo para
administración |
---
## 2. Creación de perfiles de seguridad
Se definieron nuevos perfiles para mejorar la organización de permisos.
| Perfil | Permisos principales |
|------|---------------------|
| Comercial | CRM, Ventas |
| Contabilidad | Facturación, contabilidad |
| Soporte | Helpdesk |
| Administrador | Acceso completo al sistema |
---
## 3. Limitación de acceso a módulos sensibles
Se restringió el acceso a módulos críticos:
- Ajustes
- Contabilidad
- Gestión de usuarios
- Configuración técnica
Solo accesibles para usuarios administradores o contables.
---
## 4. Verificación de funcionamiento
Se realizaron pruebas iniciando sesión con distintos perfiles.
| Usuario | Acceso correcto | Acceso bloqueado |
|------|----------------|----------------|
| Comercial | CRM, ventas | Ajustes, contabilidad |
| Contable | Facturación | Configuración técnica |
| Soporte | Helpdesk | Ventas, contabilidad |
---
## 5. Conclusión
Las modificaciones aplicadas permiten mejorar la seguridad del sistema
mediante la reducción de privilegios innecesarios y la correcta separación de
funciones entre usuarios.