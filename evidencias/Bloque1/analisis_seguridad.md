# BLOQUE 1 – Análisis de seguridad del sistema
## 1. Objetivo
- Analizar la configuración actual de seguridad del sistema ERP, revisando usuarios existentes, roles configurados, permisos asignados y accesos a módulos, con el fin de detectar riesgos y configuraciones incorrectas.
---
## 2. Usuarios existentes
- Se revisaron los usuarios registrados en el sistema desde el menú de administración de usuarios de Odoo.
| Usuario | Tipo | Estado | Grupos principales | Observaciones |
|--------|------|--------|--------------------|---------------|
| admin | Interno | Activo | Administración | Se recomienda no usar esta cuenta para tareas diarias |
| comercial1 | Interno | Activo | Ventas | Acceso coherente con su función |
| contable1 | Interno | Activo | Facturación / Contabilidad | Correcto |
| soporte1 | Interno | Activo | Usuario interno / Soporte | Revisar si requiere acceso técnico adicional |
### Observaciones generales
- Existen usuarios activos correctamente identificados.
- Se debe comprobar si hay cuentas antiguas o de prueba sin uso.
- El uso continuado de cuentas con privilegios altos supone un riesgo.
---
## 3. Roles o grupos configurados
En Odoo, los roles se gestionan mediante grupos de seguridad.
```
| Grupo / Rol | Finalidad | Nivel de acceso | Observaciones |
|-------------|-----------|-----------------|---------------|
| Administración | Gestión global del sistema | Alto | Debe limitarse a muy pocos usuarios |
| Ventas | Gestión comercial y clientes | Medio | Correcto para personal comercial |
| Contabilidad | Facturas, pagos e informes contables | Alto en datos sensibles | Debe restringirse a personal autorizado |
| Soporte | Atención e incidencias | Medio | No debería incluir permisos contables ni técnicos globales |
```
### Valoración
- La estructura de grupos debe responder al principio de mínimo privilegio. Cualquier solapamiento innecesario entre grupos aumenta el riesgo de accesos indebidos.
---
## 4. Permisos asignados
- Se revisaron los permisos asociados a varios usuarios representativos.
```
| Usuario | Permisos relevantes detectados | Valoración |
|---------|-------------------------------|-----------|
| admin | Acceso total al sistema y configuración | Correcto solo para administración |
| comercial1 | CRM, Ventas, Clientes | Correcto |
| contable1 | Facturación, contabilidad | Correcto |
| soporte1 | Acceso interno y soporte | Revisar si tiene permisos adicionales no necesarios |
```
### Análisis
- Los permisos deben estar alineados con las funciones reales de cada usuario. Si un usuario dispone de más permisos de los necesarios, se produce un exceso de privilegios.
---
## 5. Accesos a módulos
- Se revisó la visibilidad y acceso a los principales módulos del sistema.
```
| Usuario / Perfil | Módulos accesibles | Valoración |
|------------------|--------------------|-----------|
| Administrador | Ajustes, Ventas, CRM, Facturación, Inventario, Compras | Esperado |
| Comercial | CRM, Ventas, Clientes | Correcto |
| Contable | Facturación, Contabilidad | Correcto |
| Soporte | Soporte / módulos internos asignados | Revisar que no acceda a Ajustes o Contabilidad |
```
### Observaciones
- El acceso a módulos sensibles como Ajustes o Contabilidad debe estar restringido. La presencia de módulos innecesarios visibles para perfiles básicos se considera una mala práctica.
---
## 6. Riesgos detectados
- Durante el análisis se identifican los siguientes riesgos potenciales:
1. **Exceso de privilegios** en algunos perfiles si acumulan varios grupos.
2. **Uso de cuentas administrativas** para tareas cotidianas.
3. **Falta de segregación de funciones** entre áreas como ventas, soporte y contabilidad.
4. **Posibles cuentas antiguas o de prueba activas**.
5. **Acceso a módulos sensibles** por usuarios que no lo necesitan.
---
## 7. Configuraciones incorrectas detectadas
- Se detectan o se deben revisar las siguientes configuraciones:
  - Asignación de permisos demasiado amplios a determinados usuarios.
  - Posible acceso indebido al módulo Ajustes.
  - Falta de revisión periódica de usuarios activos.
  - Estructura de grupos mejorable para separar funciones.
---
## 8. Conclusión final
- La configuración de seguridad del sistema presenta una base funcional, pero requiere revisión para asegurar una asignación correcta de permisos y accesos. Se recomienda aplicar el principio de mínimo privilegio, limitar el uso de cuentas administrativas, revisar cuentas activas y reforzar la separación de funciones entre perfiles del sistema.
- Paso 11. Cómo mejorar la calidad de la entrega
- Para que quede más sólida, añade al final una sección breve con evidencias usadas:
## 9. Evidencias utilizadas
- Captura de pantalla del listado de usuarios
- Captura de los grupos o roles configurados
- Captura de permisos de al menos 3 usuarios
- Captura de módulos visibles según perfil