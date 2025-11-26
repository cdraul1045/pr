# PLAN DE PRUEBAS DE SOFTWARE
## Sistema de Gestión de Asistencia por Código QR - UPeU

**Versión:** 1.0  
**Fecha:** 2025-01-15  
**Proyecto:** Sistema de Asistencia UPeU

---

## INDICE GENERAL

1. [REQUISITOS DEL SISTEMA](#1-requisitos-del-sistema)
2. [CASOS DE PRUEBA POR SUITE](#2-casos-de-prueba-por-suite)
3. [TABLA DE CASOS DE PRUEBA](#3-tabla-de-casos-de-prueba)

---

## 1. REQUISITOS DEL SISTEMA

### 1.1 Requisitos Funcionales (RF)

| ID | Descripción |
|----|-------------|
| RF-01 | El sistema debe permitir autenticación mediante usuario y contraseña |
| RF-02 | El sistema debe validar credenciales antes de permitir acceso |
| RF-03 | El sistema debe generar token JWT al autenticarse exitosamente |
| RF-04 | El sistema debe permitir registro de nuevos usuarios con validación de campos |
| RF-05 | El sistema debe validar que el username sea único al registrar |
| RF-06 | El sistema debe validar que el correo electrónico sea válido al registrar |
| RF-07 | El sistema debe validar que el documento sea único al registrar |
| RF-08 | El sistema debe redirigir al usuario según su rol después del login (ADMIN, LIDER, INTEGRANTE, SUPERADMIN) |
| RF-09 | El sistema debe permitir cerrar sesión eliminando el token JWT |
| RF-10 | El sistema debe construir menús dinámicos según los permisos del rol del usuario |
| RF-11 | El sistema debe permitir listar todos los accesos disponibles para un usuario |
| RF-12 | El sistema debe permitir gestión completa de matrículas (crear, leer, actualizar, eliminar) |
| RF-13 | El sistema debe permitir filtrar matrículas por sede, facultad, programa, período y tipo de persona |
| RF-14 | El sistema debe permitir buscar matrículas por código de estudiante |
| RF-15 | El sistema debe permitir importación masiva de matrículas desde archivo Excel |
| RF-16 | El sistema debe validar formato de archivo Excel (.xlsx o .xls) en importación |
| RF-17 | El sistema debe requerir selección de período obligatorio para importación |
| RF-18 | El sistema debe procesar importación Excel y reportar total, exitosos y fallidos |
| RF-19 | El sistema debe permitir exportar matrículas filtradas a archivo Excel |
| RF-20 | El sistema debe permitir descargar plantilla Excel para importación |
| RF-21 | El sistema debe permitir gestión completa de sedes (CRUD) |
| RF-22 | El sistema debe validar que el nombre de sede sea único |
| RF-23 | El sistema debe permitir gestión completa de facultades (CRUD) |
| RF-24 | El sistema debe validar que el nombre de facultad sea único |
| RF-25 | El sistema debe permitir gestión completa de programas de estudio (CRUD) |
| RF-26 | El sistema debe validar que el nombre de programa sea único |
| RF-27 | El sistema debe asociar programas de estudio a una facultad |
| RF-28 | El sistema debe permitir gestión completa de períodos académicos (CRUD) |
| RF-29 | El sistema debe permitir obtener el período activo |
| RF-30 | El sistema debe permitir filtrar períodos por estado (ACTIVO, INACTIVO, FINALIZADO) |
| RF-31 | El sistema debe validar que el nombre de período sea único |
| RF-32 | El sistema debe permitir gestión completa de eventos generales (CRUD) |
| RF-33 | El sistema debe asociar eventos generales a un período y programa |
| RF-34 | El sistema debe permitir filtrar eventos generales por programa |
| RF-35 | El sistema debe permitir filtrar eventos generales por período y programa |
| RF-36 | El sistema debe permitir filtrar eventos generales solo por período |
| RF-37 | El sistema debe permitir obtener eventos activos en una fecha específica |
| RF-38 | El sistema debe permitir gestión completa de sesiones específicas (CRUD) |
| RF-39 | El sistema debe asociar sesiones específicas a un evento general |
| RF-40 | El sistema debe permitir crear sesiones recurrentes con días de semana específicos |
| RF-41 | El sistema debe permitir filtrar sesiones por evento general |
| RF-42 | El sistema debe permitir filtrar sesiones por fecha específica |
| RF-43 | El sistema debe permitir filtrar sesiones por rango de fechas y evento |
| RF-44 | El sistema debe permitir gestión completa de grupos generales (CRUD) |
| RF-45 | El sistema debe asociar grupos generales a un evento general |
| RF-46 | El sistema debe permitir filtrar grupos generales por evento general |
| RF-47 | El sistema debe permitir gestión completa de grupos pequeños (CRUD) |
| RF-48 | El sistema debe asociar grupos pequeños a un grupo general |
| RF-49 | El sistema debe permitir asignar un líder a cada grupo pequeño |
| RF-50 | El sistema debe validar que el líder no esté asignado a otro grupo pequeño |
| RF-51 | El sistema debe permitir configurar capacidad máxima de participantes por grupo pequeño |
| RF-52 | El sistema debe permitir filtrar grupos pequeños por grupo general |
| RF-53 | El sistema debe permitir filtrar grupos pequeños por líder |
| RF-54 | El sistema debe permitir obtener participantes disponibles para un evento general |
| RF-55 | El sistema debe permitir agregar participantes a un grupo pequeño |
| RF-56 | El sistema debe validar que el participante no esté ya inscrito en otro grupo del mismo evento |
| RF-57 | El sistema debe validar que el grupo no haya alcanzado su capacidad máxima |
| RF-58 | El sistema debe permitir remover participantes de un grupo pequeño (marcar como INACTIVO) |
| RF-59 | El sistema debe permitir listar participantes de un grupo pequeño |
| RF-60 | El sistema debe permitir listar grupos de un participante |
| RF-61 | El sistema debe permitir a un líder generar código QR para una sesión específica |
| RF-62 | El sistema debe validar que el líder tenga acceso a la sesión (pertenezca al grupo) |
| RF-63 | El sistema debe codificar en el QR: eventoId, fecha, hora inicio, hora fin, lugar, tolerancia |
| RF-64 | El sistema debe generar imagen QR en formato base64 |
| RF-65 | El sistema debe permitir a un integrante escanear código QR para registrar asistencia |
| RF-66 | El sistema debe validar que el QR sea del día de la sesión |
| RF-67 | El sistema debe validar que el registro esté dentro de la ventana permitida (30 min antes - 2 horas después) |
| RF-68 | El sistema debe validar que el integrante pertenezca al evento |
| RF-69 | El sistema debe prevenir registros duplicados de asistencia para la misma sesión |
| RF-70 | El sistema debe determinar automáticamente el estado (PRESENTE o TARDE) según tolerancia |
| RF-71 | El sistema debe permitir a un líder obtener lista de participantes para llamado |
| RF-72 | El sistema debe mostrar estado de asistencia de cada participante (PRESENTE, TARDE, AUSENTE, JUSTIFICADO, PENDIENTE) |
| RF-73 | El sistema debe permitir a un líder marcar asistencia manualmente |
| RF-74 | El sistema debe validar que el participante pertenezca al grupo del líder |
| RF-75 | El sistema debe permitir marcar asistencia como PRESENTE, TARDE, AUSENTE o JUSTIFICADO |
| RF-76 | El sistema debe permitir agregar observación al marcar asistencia |
| RF-77 | El sistema debe permitir consultar todas las asistencias registradas |
| RF-78 | El sistema debe permitir filtrar asistencias por sesión específica |
| RF-79 | El sistema debe permitir filtrar asistencias por persona |
| RF-80 | El sistema debe permitir generar reporte consolidado de asistencias por evento general |
| RF-81 | El sistema debe calcular porcentaje de asistencia por participante en el reporte |
| RF-82 | El sistema debe mostrar totales de sesiones, presentes, tardes, ausentes y justificados por participante |
| RF-83 | El sistema debe permitir a un líder visualizar sus grupos asignados |
| RF-84 | El sistema debe permitir a un líder consultar asistencias de sus grupos |
| RF-85 | El sistema debe permitir a un integrante consultar su historial personal de asistencias |
| RF-86 | El sistema debe mostrar dashboard administrativo con estadísticas (total personas, eventos activos, asistencias hoy, total matrículas) |
| RF-87 | El sistema debe mostrar dashboard de líder con estadísticas (total grupos, participantes, asistencias registradas, porcentaje promedio) |
| RF-88 | El sistema debe mostrar dashboard de integrante con estadísticas básicas |
| RF-89 | El sistema debe permitir gestión completa de personas (CRUD) |
| RF-90 | El sistema debe permitir buscar persona por código de estudiante |
| RF-91 | El sistema debe validar que el código de estudiante sea único |
| RF-92 | El sistema debe validar que el documento de persona sea único |
| RF-93 | El sistema debe permitir obtener usuarios por rol |
| RF-94 | El sistema debe permitir obtener líderes disponibles (no asignados a grupos) |

### 1.2 Requisitos No Funcionales (RNF)

| ID | Descripción |
|----|-------------|
| RNF-01 | El sistema debe responder a peticiones HTTP en menos de 2 segundos para operaciones CRUD básicas |
| RNF-02 | El sistema debe soportar al menos 50 usuarios concurrentes |
| RNF-03 | El sistema debe mantener disponibilidad del 99% durante horario laboral |
| RNF-04 | El sistema debe utilizar autenticación JWT con tokens que expiran en 5 horas |
| RNF-05 | El sistema debe almacenar contraseñas encriptadas con BCrypt |
| RNF-06 | El sistema debe validar tokens JWT en cada petición a endpoints protegidos |
| RNF-07 | El sistema debe manejar errores y retornar mensajes descriptivos en formato JSON |
| RNF-08 | El sistema debe validar datos de entrada antes de procesarlos |
| RNF-09 | El sistema debe prevenir inyección SQL mediante uso de JPA/Hibernate |
| RNF-10 | El sistema debe permitir CORS desde cualquier origen para desarrollo |
| RNF-11 | El sistema debe mantener integridad referencial en la base de datos |
| RNF-12 | El sistema debe validar constraints de unicidad en base de datos |
| RNF-13 | El sistema debe manejar transacciones atómicas en operaciones complejas |
| RNF-14 | El sistema debe ser compatible con navegadores modernos (Chrome, Firefox, Edge, Safari) |
| RNF-15 | El sistema debe ser responsive y adaptable a dispositivos móviles |
| RNF-16 | El sistema debe generar códigos QR legibles en dispositivos móviles estándar |
| RNF-17 | El sistema debe procesar archivos Excel de hasta 10MB |
| RNF-18 | El sistema debe validar formato de archivos Excel antes de procesar |
| RNF-19 | El sistema debe mantener logs de errores para diagnóstico |
| RNF-20 | El sistema debe utilizar codificación UTF-8 para caracteres especiales |

---

## 2. CASOS DE PRUEBA POR SUITE

### 2.1 AUTENTICACIÓN

TC-AUT-001 – Login exitoso con credenciales válidas de usuario Admin  
TC-AUT-002 – Login exitoso con credenciales válidas de usuario Líder  
TC-AUT-003 – Login exitoso con credenciales válidas de usuario Integrante  
TC-AUT-004 – Login exitoso con credenciales válidas de usuario SuperAdmin  
TC-AUT-005 – Login fallido con credenciales inválidas (password incorrecto)  
TC-AUT-006 – Login fallido con usuario inexistente  
TC-AUT-007 – Validación de campos vacíos en formulario de login  
TC-AUT-008 – Persistencia de token JWT en localStorage después de login exitoso  
TC-AUT-009 – Redirección automática según rol después de login (ADMIN → /dashboard/admin)  
TC-AUT-010 – Redirección automática según rol después de login (LIDER → /dashboard/lider)  
TC-AUT-011 – Redirección automática según rol después de login (INTEGRANTE → /dashboard/integrante)  
TC-AUT-012 – Redirección automática según rol después de login (SUPERADMIN → /superadmin)  
TC-AUT-013 – Logout elimina token JWT y datos de usuario de localStorage  
TC-AUT-014 – Logout redirige a página de login  
TC-AUT-015 – Registro exitoso de nuevo usuario con datos válidos  
TC-AUT-016 – Registro fallido con username duplicado  
TC-AUT-017 – Registro fallido con correo electrónico inválido  
TC-AUT-018 – Registro fallido con documento duplicado  
TC-AUT-019 – Validación de campos requeridos en formulario de registro  
TC-AUT-020 – Validación de coincidencia de contraseñas en registro  
TC-AUT-021 – Validación de token JWT expirado  
TC-AUT-022 – Validación de token JWT inválido o malformado  
TC-AUT-023 – Acceso denegado a rutas protegidas sin token JWT  
TC-AUT-024 – Redirección de usuario autenticado que intenta acceder a /login

### 2.2 GESTIÓN DE USUARIOS, ROLES Y PERMISOS

TC-USU-001 – Obtener lista de accesos disponibles para un usuario  
TC-USU-002 – Obtener menú estructurado por rol de usuario  
TC-USU-003 – Menú dinámico muestra solo opciones permitidas para rol ADMIN  
TC-USU-004 – Menú dinámico muestra solo opciones permitidas para rol LIDER  
TC-USU-005 – Menú dinámico muestra solo opciones permitidas para rol INTEGRANTE  
TC-USU-006 – Menú dinámico muestra todas las opciones para rol SUPERADMIN  
TC-USU-007 – Obtener usuarios filtrados por rol (ADMIN)  
TC-USU-008 – Obtener usuarios filtrados por rol (LIDER)  
TC-USU-009 – Obtener usuarios filtrados por rol (INTEGRANTE)  
TC-USU-010 – Obtener líderes disponibles (no asignados a grupos)  
TC-USU-011 – Obtener líderes disponibles excluyendo un grupo específico  
TC-USU-012 – Acceso restringido: Integrante intenta acceder a ruta de Admin  
TC-USU-013 – Acceso restringido: Líder intenta acceder a ruta de Admin  
TC-USU-014 – Acceso restringido: Admin intenta acceder a ruta de SuperAdmin

### 2.3 GESTIÓN DE MATRÍCULAS

TC-MAT-001 – Listar todas las matrículas  
TC-MAT-002 – Obtener matrícula por ID  
TC-MAT-003 – Buscar matrículas por código de estudiante  
TC-MAT-004 – Filtrar matrículas por sede  
TC-MAT-005 – Filtrar matrículas por facultad  
TC-MAT-006 – Filtrar matrículas por programa  
TC-MAT-007 – Filtrar matrículas por período  
TC-MAT-008 – Filtrar matrículas por tipo de persona (ESTUDIANTE/INVITADO)  
TC-MAT-009 – Filtrar matrículas con múltiples criterios combinados  
TC-MAT-010 – Crear nueva matrícula con datos válidos  
TC-MAT-011 – Actualizar matrícula existente  
TC-MAT-012 – Eliminar matrícula  
TC-MAT-013 – Importar matrículas desde Excel con archivo válido  
TC-MAT-014 – Importar matrículas con período seleccionado  
TC-MAT-015 – Importar matrículas con filtros aplicados (sede, facultad, programa)  
TC-MAT-016 – Importar matrículas falla con archivo no Excel  
TC-MAT-017 – Importar matrículas falla sin seleccionar período  
TC-MAT-018 – Importar matrículas falla con archivo vacío  
TC-MAT-019 – Importar matrículas reporta total, exitosos y fallidos  
TC-MAT-020 – Exportar matrículas a Excel sin filtros  
TC-MAT-021 – Exportar matrículas a Excel con filtros aplicados  
TC-MAT-022 – Descargar plantilla Excel para importación  
TC-MAT-023 – Validar formato de archivo Excel descargado

### 2.4 GESTIÓN DE ESTRUCTURA ACADÉMICA

#### 2.4.1 Sedes

TC-SED-001 – Listar todas las sedes  
TC-SED-002 – Obtener sede por ID  
TC-SED-003 – Crear nueva sede con datos válidos  
TC-SED-004 – Crear sede falla con nombre duplicado  
TC-SED-005 – Actualizar sede existente  
TC-SED-006 – Eliminar sede  
TC-SED-007 – Eliminar sede falla si tiene matrículas asociadas

#### 2.4.2 Facultades

TC-FAC-001 – Listar todas las facultades  
TC-FAC-002 – Obtener facultad por ID  
TC-FAC-003 – Crear nueva facultad con datos válidos  
TC-FAC-004 – Crear facultad falla con nombre duplicado  
TC-FAC-005 – Actualizar facultad existente  
TC-FAC-006 – Eliminar facultad  
TC-FAC-007 – Eliminar facultad falla si tiene programas asociados

#### 2.4.3 Programas de Estudio

TC-PRO-001 – Listar todos los programas de estudio  
TC-PRO-002 – Obtener programa por ID  
TC-PRO-003 – Crear nuevo programa con facultad válida  
TC-PRO-004 – Crear programa falla con nombre duplicado  
TC-PRO-005 – Crear programa falla sin facultad asociada  
TC-PRO-006 – Actualizar programa existente  
TC-PRO-007 – Eliminar programa  
TC-PRO-008 – Eliminar programa falla si tiene matrículas asociadas

#### 2.4.4 Períodos

TC-PER-001 – Listar todos los períodos  
TC-PER-002 – Obtener período por ID  
TC-PER-003 – Obtener período activo  
TC-PER-004 – Filtrar períodos por estado (ACTIVO)  
TC-PER-005 – Filtrar períodos por estado (INACTIVO)  
TC-PER-006 – Filtrar períodos por estado (FINALIZADO)  
TC-PER-007 – Crear nuevo período con datos válidos  
TC-PER-008 – Crear período falla con nombre duplicado  
TC-PER-009 – Validar que fecha fin sea posterior a fecha inicio  
TC-PER-010 – Actualizar período existente  
TC-PER-011 – Eliminar período

### 2.5 GESTIÓN DE EVENTOS GENERALES

TC-EVE-001 – Listar todos los eventos generales  
TC-EVE-002 – Obtener evento general por ID  
TC-EVE-003 – Filtrar eventos generales por programa  
TC-EVE-004 – Filtrar eventos generales por período y programa  
TC-EVE-005 – Filtrar eventos generales solo por período  
TC-EVE-006 – Obtener eventos activos en fecha específica  
TC-EVE-007 – Crear nuevo evento general con período y programa válidos  
TC-EVE-008 – Crear evento general falla sin período  
TC-EVE-009 – Crear evento general falla sin programa  
TC-EVE-010 – Validar que fecha fin sea posterior a fecha inicio  
TC-EVE-011 – Actualizar evento general existente  
TC-EVE-012 – Eliminar evento general  
TC-EVE-013 – Eliminar evento general falla si tiene sesiones asociadas

### 2.6 GESTIÓN DE SESIONES (EVENTOS ESPECÍFICOS)

TC-SES-001 – Listar todas las sesiones  
TC-SES-002 – Obtener sesión por ID  
TC-SES-003 – Filtrar sesiones por evento general  
TC-SES-004 – Filtrar sesiones por fecha específica  
TC-SES-005 – Filtrar sesiones por rango de fechas y evento  
TC-SES-006 – Crear sesión individual con datos válidos  
TC-SES-007 – Crear sesión falla sin evento general asociado  
TC-SES-008 – Validar que hora fin sea posterior a hora inicio  
TC-SES-009 – Crear sesiones recurrentes con días de semana específicos  
TC-SES-010 – Crear recurrencia genera múltiples sesiones según días seleccionados  
TC-SES-011 – Crear recurrencia respeta rango de fechas especificado  
TC-SES-012 – Actualizar sesión existente  
TC-SES-013 – Eliminar sesión  
TC-SES-014 – Eliminar sesión falla si tiene asistencias registradas

### 2.7 GESTIÓN DE GRUPOS GENERALES

TC-GRG-001 – Listar todos los grupos generales  
TC-GRG-002 – Obtener grupo general por ID  
TC-GRG-003 – Filtrar grupos generales por evento general  
TC-GRG-004 – Crear nuevo grupo general con evento general válido  
TC-GRG-005 – Crear grupo general falla sin evento general asociado  
TC-GRG-006 – Actualizar grupo general existente  
TC-GRG-007 – Eliminar grupo general  
TC-GRG-008 – Eliminar grupo general falla si tiene grupos pequeños asociados

### 2.8 GESTIÓN DE GRUPOS PEQUEÑOS

TC-GRP-001 – Listar todos los grupos pequeños  
TC-GRP-002 – Obtener grupo pequeño por ID  
TC-GRP-003 – Filtrar grupos pequeños por grupo general  
TC-GRP-004 – Filtrar grupos pequeños por líder  
TC-GRP-005 – Obtener participantes disponibles para un evento general  
TC-GRP-006 – Crear nuevo grupo pequeño con grupo general y líder válidos  
TC-GRP-007 – Crear grupo pequeño falla sin grupo general  
TC-GRP-008 – Crear grupo pequeño falla sin líder asignado  
TC-GRP-009 – Crear grupo pequeño falla si el líder ya está asignado a otro grupo  
TC-GRP-010 – Configurar capacidad máxima de participantes  
TC-GRP-011 – Actualizar grupo pequeño existente  
TC-GRP-012 – Eliminar grupo pequeño  
TC-GRP-013 – Eliminar grupo pequeño falla si tiene participantes activos

### 2.9 GESTIÓN DE PARTICIPANTES EN GRUPOS

TC-PAR-001 – Listar participantes de un grupo pequeño  
TC-PAR-002 – Listar grupos de un participante  
TC-PAR-003 – Agregar participante a grupo pequeño con capacidad disponible  
TC-PAR-004 – Agregar participante falla si el grupo alcanzó capacidad máxima  
TC-PAR-005 – Agregar participante falla si ya está inscrito en otro grupo del mismo evento  
TC-PAR-006 – Agregar participante falla si el participante no existe  
TC-PAR-007 – Agregar participante falla si el grupo pequeño no existe  
TC-PAR-008 – Remover participante de grupo pequeño (marcar como INACTIVO)  
TC-PAR-009 – Participante removido queda disponible para otros grupos  
TC-PAR-010 – Eliminar participante de grupo pequeño

### 2.10 REGISTRO DE ASISTENCIAS CON QR

TC-QR-001 – Líder genera código QR para sesión del día actual  
TC-QR-002 – Líder genera QR falla si no es líder del grupo de la sesión  
TC-QR-003 – QR generado contiene datos correctos (eventoId, fecha, hora, lugar, tolerancia)  
TC-QR-004 – QR generado retorna imagen en formato base64  
TC-QR-005 – Integrante escanea QR válido y registra asistencia exitosamente  
TC-QR-006 – Escaneo QR falla si la sesión no es del día actual  
TC-QR-007 – Escaneo QR falla si está fuera de ventana permitida (30 min antes - 2 horas después)  
TC-QR-008 – Escaneo QR falla si el integrante no pertenece al evento  
TC-QR-009 – Escaneo QR falla si ya existe asistencia registrada para esa sesión  
TC-QR-010 – Sistema determina estado PRESENTE cuando se registra dentro de tolerancia  
TC-QR-011 – Sistema determina estado TARDE cuando se registra después de tolerancia  
TC-QR-012 – Escaneo QR registra coordenadas GPS opcionales  
TC-QR-013 – Escaneo QR permite agregar observación

### 2.11 GESTIÓN DE ASISTENCIAS (LÍDER)

TC-ASI-001 – Líder obtiene lista de participantes para llamado de sesión  
TC-ASI-002 – Lista de llamado muestra estado de asistencia de cada participante  
TC-ASI-003 – Lista de llamado muestra participantes con estado PENDIENTE inicialmente  
TC-ASI-004 – Líder marca asistencia manualmente como PRESENTE  
TC-ASI-005 – Líder marca asistencia manualmente como TARDE  
TC-ASI-006 – Líder marca asistencia manualmente como AUSENTE  
TC-ASI-007 – Líder marca asistencia manualmente como JUSTIFICADO con motivo  
TC-ASI-008 – Marcar asistencia falla si el participante no pertenece al grupo del líder  
TC-ASI-009 – Marcar asistencia permite agregar observación  
TC-ASI-010 – Líder consulta todas las asistencias de sus grupos  
TC-ASI-011 – Líder consulta asistencias filtradas por sesión específica

### 2.12 CONSULTA DE ASISTENCIAS

TC-CON-001 – Consultar todas las asistencias registradas  
TC-CON-002 – Filtrar asistencias por sesión específica  
TC-CON-003 – Filtrar asistencias por persona  
TC-CON-004 – Integrante consulta su historial personal de asistencias  
TC-CON-005 – Historial muestra sesión, fecha, hora, estado y observación  
TC-CON-006 – Líder consulta asistencias de sus grupos

### 2.13 REPORTES Y CONSULTAS

TC-REP-001 – Generar reporte consolidado de asistencias por evento general  
TC-REP-002 – Reporte muestra lista de participantes del evento  
TC-REP-003 – Reporte calcula total de sesiones por participante  
TC-REP-004 – Reporte calcula total de asistencias PRESENTE por participante  
TC-REP-005 – Reporte calcula total de asistencias TARDE por participante  
TC-REP-006 – Reporte calcula total de asistencias AUSENTE por participante  
TC-REP-007 – Reporte calcula total de asistencias JUSTIFICADO por participante  
TC-REP-008 – Reporte calcula porcentaje de asistencia por participante  
TC-REP-009 – Generar reporte falla si el evento general no existe  
TC-REP-010 – Reporte muestra datos correctos cuando hay asistencias registradas  
TC-REP-011 – Reporte muestra mensaje cuando no hay datos de asistencia

### 2.14 DASHBOARDS

TC-DAS-001 – Dashboard Admin muestra estadísticas (total personas, eventos activos, asistencias hoy, total matrículas)  
TC-DAS-002 – Dashboard Admin carga estadísticas correctamente  
TC-DAS-003 – Dashboard Líder muestra estadísticas (total grupos, participantes, asistencias registradas, porcentaje promedio)  
TC-DAS-004 – Dashboard Líder carga estadísticas correctamente para el líder autenticado  
TC-DAS-005 – Dashboard Integrante muestra estadísticas básicas  
TC-DAS-006 – Dashboard SuperAdmin muestra estadísticas del sistema  
TC-DAS-007 – Dashboard muestra estado de carga mientras obtiene datos  
TC-DAS-008 – Dashboard muestra mensaje de error si falla la carga de datos

### 2.15 GESTIÓN DE PERSONAS

TC-PER-001 – Listar todas las personas  
TC-PER-002 – Obtener persona por ID  
TC-PER-003 – Buscar persona por código de estudiante  
TC-PER-004 – Crear nueva persona con datos válidos  
TC-PER-005 – Crear persona falla con código de estudiante duplicado  
TC-PER-006 – Crear persona falla con documento duplicado  
TC-PER-007 – Actualizar persona existente  
TC-PER-008 – Eliminar persona

### 2.16 SEGURIDAD

TC-SEG-001 – Validación de token JWT en petición a endpoint protegido  
TC-SEG-002 – Acceso denegado (401) sin token JWT  
TC-SEG-003 – Acceso denegado (401) con token JWT inválido  
TC-SEG-004 – Acceso denegado (401) con token JWT expirado  
TC-SEG-005 – Validación de rol en endpoints que requieren permisos específicos  
TC-SEG-006 – Prevención de inyección SQL en consultas  
TC-SEG-007 – Validación de datos de entrada en todos los endpoints  
TC-SEG-008 – Contraseñas almacenadas encriptadas con BCrypt  
TC-SEG-009 – CORS configurado para permitir solicitudes desde frontend  
TC-SEG-010 – Manejo seguro de errores sin exponer información sensible

### 2.17 BASE DE DATOS

TC-BD-001 – Integridad referencial: Eliminar sede falla si tiene matrículas asociadas  
TC-BD-002 – Integridad referencial: Eliminar facultad falla si tiene programas asociados  
TC-BD-003 – Integridad referencial: Eliminar programa falla si tiene matrículas asociadas  
TC-BD-004 – Integridad referencial: Eliminar evento general falla si tiene sesiones asociadas  
TC-BD-005 – Integridad referencial: Eliminar grupo general falla si tiene grupos pequeños asociados  
TC-BD-006 – Integridad referencial: Eliminar grupo pequeño falla si tiene participantes activos  
TC-BD-007 – Constraint de unicidad: Username duplicado genera error  
TC-BD-008 – Constraint de unicidad: Código de estudiante duplicado genera error  
TC-BD-009 – Constraint de unicidad: Documento duplicado genera error  
TC-BD-010 – Constraint de unicidad: Nombre de sede duplicado genera error  
TC-BD-011 – Constraint de unicidad: Nombre de facultad duplicado genera error  
TC-BD-012 – Constraint de unicidad: Nombre de programa duplicado genera error  
TC-BD-013 – Constraint de unicidad: Nombre de período duplicado genera error  
TC-BD-014 – Constraint de unicidad: Asistencia duplicada (misma sesión y persona) genera error  
TC-BD-015 – Transacción atómica: Crear evento con sesiones (rollback si falla alguna sesión)  
TC-BD-016 – Transacción atómica: Importar matrículas (rollback si falla validación crítica)

### 2.18 ERRORES Y EXCEPCIONES

TC-ERR-001 – Manejo de error 400 (Bad Request) con mensaje descriptivo  
TC-ERR-002 – Manejo de error 401 (Unauthorized) con mensaje descriptivo  
TC-ERR-003 – Manejo de error 404 (Not Found) con mensaje descriptivo  
TC-ERR-004 – Manejo de error 500 (Internal Server Error) con mensaje genérico  
TC-ERR-005 – Validación de campos requeridos retorna mensaje específico por campo  
TC-ERR-006 – Validación de formato de email retorna mensaje descriptivo  
TC-ERR-007 – Manejo de excepción ModelNotFoundException  
TC-ERR-008 – Manejo de excepción RuntimeException con mensaje de negocio  
TC-ERR-009 – Manejo de excepción MethodArgumentNotValidException  
TC-ERR-010 – Respuesta de error en formato JSON consistente (CustomResponse)

### 2.19 RENDIMIENTO Y STRESS

TC-REN-001 – Tiempo de respuesta de login menor a 1 segundo  
TC-REN-002 – Tiempo de respuesta de listado de matrículas menor a 2 segundos  
TC-REN-003 – Tiempo de respuesta de importación Excel menor a 30 segundos para 1000 registros  
TC-REN-004 – Tiempo de respuesta de generación de QR menor a 500ms  
TC-REN-005 – Tiempo de respuesta de escaneo QR menor a 1 segundo  
TC-REN-006 – Sistema soporta 50 usuarios concurrentes en login  
TC-REN-007 – Sistema soporta 100 peticiones concurrentes a API  
TC-REN-008 – Generación de reporte para evento con 500 participantes menor a 5 segundos

### 2.20 COMPATIBILIDAD

TC-COM-001 – Sistema funciona correctamente en Chrome (últimas 2 versiones)  
TC-COM-002 – Sistema funciona correctamente en Firefox (últimas 2 versiones)  
TC-COM-003 – Sistema funciona correctamente en Edge (últimas 2 versiones)  
TC-COM-004 – Sistema funciona correctamente en Safari (últimas 2 versiones)  
TC-COM-005 – Escaneo QR funciona en dispositivos móviles Android  
TC-COM-006 – Escaneo QR funciona en dispositivos móviles iOS  
TC-COM-007 – Interfaz responsive se adapta a pantallas móviles  
TC-COM-008 – Interfaz responsive se adapta a tablets

---

## 3. TABLA DE CASOS DE PRUEBA

| Suite | ID | Título | Precondiciones | Pasos | Resultado Esperado | Prioridad | Tipo | Requisitos | Responsable |
|-------|----|----|----|----|----|----|----|----|----|
| Autenticación | TC-AUT-001 | Login exitoso con credenciales válidas de usuario Admin | Usuario Admin existe en BD con estado ACTIVO. API accesible. | 1. Abrir aplicación en navegador<br>2. Acceder a /login<br>3. Ingresar username: admin<br>4. Ingresar password: admin123<br>5. Click en "Ingresar" | Se autentica exitosamente, se genera token JWT, se almacena en localStorage, se redirige a /dashboard/admin, se muestra menú de Admin. | P1 | Funcional/API | RF-01, RF-02, RF-03, RF-08 | Tester |
| Autenticación | TC-AUT-002 | Login exitoso con credenciales válidas de usuario Líder | Usuario Líder existe en BD con estado ACTIVO. | 1. Abrir /login<br>2. Ingresar credenciales de líder<br>3. Click en "Ingresar" | Se autentica exitosamente, token almacenado, redirección a /dashboard/lider, menú de Líder visible. | P1 | Funcional/API | RF-01, RF-02, RF-03, RF-08 | Tester |
| Autenticación | TC-AUT-003 | Login exitoso con credenciales válidas de usuario Integrante | Usuario Integrante existe en BD con estado ACTIVO. | 1. Abrir /login<br>2. Ingresar credenciales de integrante<br>3. Click en "Ingresar" | Se autentica exitosamente, token almacenado, redirección a /dashboard/integrante, menú de Integrante visible. | P1 | Funcional/API | RF-01, RF-02, RF-03, RF-08 | Tester |
| Autenticación | TC-AUT-004 | Login exitoso con credenciales válidas de usuario SuperAdmin | Usuario SuperAdmin existe en BD con estado ACTIVO. | 1. Abrir /login<br>2. Ingresar credenciales de superadmin<br>3. Click en "Ingresar" | Se autentica exitosamente, token almacenado, redirección a /superadmin, menú completo visible. | P1 | Funcional/API | RF-01, RF-02, RF-03, RF-08 | Tester |
| Autenticación | TC-AUT-005 | Login fallido con credenciales inválidas (password incorrecto) | Usuario existe en BD. | 1. Abrir /login<br>2. Ingresar username válido<br>3. Ingresar password incorrecto<br>4. Click en "Ingresar" | Se muestra mensaje de error "Credenciales incorrectas", no se genera token, usuario permanece en página de login. | P1 | Funcional/API | RF-02 | Tester |
| Autenticación | TC-AUT-006 | Login fallido con usuario inexistente | Usuario NO existe en BD. | 1. Abrir /login<br>2. Ingresar username inexistente<br>3. Ingresar cualquier password<br>4. Click en "Ingresar" | Se muestra mensaje de error, no se genera token, usuario permanece en página de login. | P1 | Funcional/API | RF-02 | Tester |
| Autenticación | TC-AUT-007 | Validación de campos vacíos en formulario de login | Ninguna. | 1. Abrir /login<br>2. Dejar campos vacíos<br>3. Click en "Ingresar" | Se muestra mensaje "Por favor completa todos los campos", no se envía petición al servidor. | P2 | UI/Validación | RF-02 | Tester |
| Autenticación | TC-AUT-008 | Persistencia de token JWT en localStorage después de login exitoso | Usuario autenticado. | 1. Login exitoso<br>2. Verificar localStorage en DevTools | Token JWT almacenado en localStorage con clave "token", datos de usuario almacenados con clave "user". | P1 | Funcional | RF-03 | Tester |
| Autenticación | TC-AUT-009 | Redirección automática según rol después de login (ADMIN → /dashboard/admin) | Usuario Admin autenticado. | 1. Login como Admin<br>2. Observar redirección | Redirección automática a /dashboard/admin, dashboard de Admin visible. | P1 | Funcional | RF-08 | Tester |
| Autenticación | TC-AUT-010 | Redirección automática según rol después de login (LIDER → /dashboard/lider) | Usuario Líder autenticado. | 1. Login como Líder<br>2. Observar redirección | Redirección automática a /dashboard/lider, dashboard de Líder visible. | P1 | Funcional | RF-08 | Tester |
| Autenticación | TC-AUT-011 | Redirección automática según rol después de login (INTEGRANTE → /dashboard/integrante) | Usuario Integrante autenticado. | 1. Login como Integrante<br>2. Observar redirección | Redirección automática a /dashboard/integrante, dashboard de Integrante visible. | P1 | Funcional | RF-08 | Tester |
| Autenticación | TC-AUT-012 | Redirección automática según rol después de login (SUPERADMIN → /superadmin) | Usuario SuperAdmin autenticado. | 1. Login como SuperAdmin<br>2. Observar redirección | Redirección automática a /superadmin, dashboard de SuperAdmin visible. | P1 | Funcional | RF-08 | Tester |
| Autenticación | TC-AUT-013 | Logout elimina token JWT y datos de usuario de localStorage | Usuario autenticado. | 1. Usuario autenticado en sistema<br>2. Click en "Cerrar Sesión"<br>3. Verificar localStorage | Token eliminado de localStorage, datos de usuario eliminados, localStorage limpio. | P1 | Funcional | RF-09 | Tester |
| Autenticación | TC-AUT-014 | Logout redirige a página de login | Usuario autenticado. | 1. Usuario autenticado<br>2. Click en "Cerrar Sesión" | Redirección a /login, página de login visible. | P1 | Funcional | RF-09 | Tester |
| Autenticación | TC-AUT-015 | Registro exitoso de nuevo usuario con datos válidos | No existe usuario con mismo username/documento/correo. | 1. Abrir /register<br>2. Completar formulario: username, nombreCompleto, correo válido, documento único, password, confirmPassword<br>3. Click en "Registrarse" | Usuario creado en BD, mensaje de éxito, redirección a /login, usuario puede iniciar sesión. | P1 | Funcional/API | RF-04, RF-05, RF-06, RF-07 | Tester |
| Autenticación | TC-AUT-016 | Registro fallido con username duplicado | Usuario con mismo username ya existe. | 1. Abrir /register<br>2. Ingresar username existente<br>3. Completar resto del formulario<br>4. Click en "Registrarse" | Mensaje de error "El nombre de usuario ya está en uso", usuario no creado. | P1 | Funcional/Validación | RF-05 | Tester |
| Autenticación | TC-AUT-017 | Registro fallido con correo electrónico inválido | Ninguna. | 1. Abrir /register<br>2. Ingresar correo con formato inválido (ej: "correo_sin_arroba")<br>3. Completar resto del formulario<br>4. Click en "Registrarse" | Mensaje de error "Debe ser un correo válido", usuario no creado. | P1 | Validación | RF-06 | Tester |
| Autenticación | TC-AUT-018 | Registro fallido con documento duplicado | Persona con mismo documento ya existe. | 1. Abrir /register<br>2. Ingresar documento existente<br>3. Completar resto del formulario<br>4. Click en "Registrarse" | Mensaje de error "El número de documento ya está registrado", usuario no creado. | P1 | Funcional/Validación | RF-07 | Tester |
| Autenticación | TC-AUT-019 | Validación de campos requeridos en formulario de registro | Ninguna. | 1. Abrir /register<br>2. Dejar algún campo requerido vacío<br>3. Click en "Registrarse" | Navegador muestra validación HTML, no se envía formulario, campos requeridos marcados. | P2 | UI/Validación | RF-04 | Tester |
| Autenticación | TC-AUT-020 | Validación de coincidencia de contraseñas en registro | Ninguna. | 1. Abrir /register<br>2. Ingresar password<br>3. Ingresar confirmPassword diferente<br>4. Click en "Registrarse" | Mensaje "Las contraseñas no coinciden", usuario no creado. | P1 | Validación | RF-04 | Tester |
| Autenticación | TC-AUT-021 | Validación de token JWT expirado | Token JWT expirado almacenado. | 1. Tener token expirado en localStorage<br>2. Intentar acceder a ruta protegida | Token detectado como expirado, eliminado de localStorage, redirección a /login. | P1 | Seguridad | RNF-04 | Tester |
| Autenticación | TC-AUT-022 | Validación de token JWT inválido o malformado | Token malformado almacenado. | 1. Modificar token en localStorage a formato inválido<br>2. Intentar acceder a ruta protegida | Token detectado como inválido, eliminado, redirección a /login. | P1 | Seguridad | RNF-04 | Tester |
| Autenticación | TC-AUT-023 | Acceso denegado a rutas protegidas sin token JWT | No hay token en localStorage. | 1. Limpiar localStorage<br>2. Intentar acceder a /dashboard/admin | Redirección a /login, mensaje de acceso denegado. | P1 | Seguridad | RNF-06 | Tester |
| Autenticación | TC-AUT-024 | Redirección de usuario autenticado que intenta acceder a /login | Usuario autenticado con token válido. | 1. Usuario autenticado<br>2. Intentar acceder a /login | Redirección automática a dashboard según rol, no se muestra página de login. | P2 | Funcional | RF-08 | Tester |
| Gestión de Usuarios, Roles y Permisos | TC-USU-001 | Obtener lista de accesos disponibles para un usuario | Usuario autenticado. | 1. Login como cualquier rol<br>2. Realizar POST a /accesos/user con username en body | Respuesta 200 OK con lista de AccesoDTO, cada acceso tiene id, nombre, url, icono. | P2 | API | RF-10, RF-11 | Tester |
| Gestión de Usuarios, Roles y Permisos | TC-USU-002 | Obtener menú estructurado por rol de usuario | Usuario autenticado. | 1. Login como cualquier rol<br>2. Realizar POST a /accesos/menu con username en body | Respuesta 200 OK con lista de MenuGroup, estructura jerárquica con items. | P1 | API | RF-10 | Tester |
| Gestión de Usuarios, Roles y Permisos | TC-USU-003 | Menú dinámico muestra solo opciones permitidas para rol ADMIN | Usuario Admin autenticado. | 1. Login como Admin<br>2. Observar menú lateral (Sidebar) | Menú muestra: Matrículas, Importar Excel, Sedes, Facultades, Programas, Eventos Generales, Sesiones, Grupos Generales, Grupos Pequeños, Reportes, Dashboard Admin. No muestra opciones de Líder o Integrante. | P1 | UI/Funcional | RF-10 | Tester |
| Gestión de Usuarios, Roles y Permisos | TC-USU-004 | Menú dinámico muestra solo opciones permitidas para rol LIDER | Usuario Líder autenticado. | 1. Login como Líder<br>2. Observar menú lateral | Menú muestra: Dashboard Líder, Mis Grupos, Registrar Asistencia, Ver Asistencias, Mis Asistencias. No muestra opciones de Admin. | P1 | UI/Funcional | RF-10 | Tester |
| Gestión de Usuarios, Roles y Permisos | TC-USU-005 | Menú dinámico muestra solo opciones permitidas para rol INTEGRANTE | Usuario Integrante autenticado. | 1. Login como Integrante<br>2. Observar menú lateral | Menú muestra: Dashboard Integrante, Escanear QR, Mis Asistencias. No muestra opciones de Admin o Líder. | P1 | UI/Funcional | RF-10 | Tester |
| Gestión de Usuarios, Roles y Permisos | TC-USU-006 | Menú dinámico muestra todas las opciones para rol SUPERADMIN | Usuario SuperAdmin autenticado. | 1. Login como SuperAdmin<br>2. Observar menú lateral | Menú muestra todas las opciones del sistema sin restricciones. | P1 | UI/Funcional | RF-10 | Tester |
| Gestión de Usuarios, Roles y Permisos | TC-USU-007 | Obtener usuarios filtrados por rol (ADMIN) | Usuarios con rol ADMIN existen. | 1. Login como Admin<br>2. Realizar GET a /users/rol/ADMIN | Respuesta 200 OK con lista de UsuarioDTO con rol ADMIN. | P2 | API | RF-93 | Tester |
| Gestión de Usuarios, Roles y Permisos | TC-USU-008 | Obtener usuarios filtrados por rol (LIDER) | Usuarios con rol LIDER existen. | 1. Login como Admin<br>2. Realizar GET a /users/rol/LIDER | Respuesta 200 OK con lista de UsuarioDTO con rol LIDER. | P2 | API | RF-93 | Tester |
| Gestión de Usuarios, Roles y Permisos | TC-USU-009 | Obtener usuarios filtrados por rol (INTEGRANTE) | Usuarios con rol INTEGRANTE existen. | 1. Login como Admin<br>2. Realizar GET a /users/rol/INTEGRANTE | Respuesta 200 OK con lista de UsuarioDTO con rol INTEGRANTE. | P2 | API | RF-93 | Tester |
| Gestión de Usuarios, Roles y Permisos | TC-USU-010 | Obtener líderes disponibles (no asignados a grupos) | Líderes sin grupo asignado existen. | 1. Login como Admin<br>2. Realizar GET a /users/lideres-disponibles | Respuesta 200 OK con lista de PersonaDTO que son líderes y no están asignados a grupos. | P1 | API | RF-94 | Tester |
| Gestión de Usuarios, Roles y Permisos | TC-USU-011 | Obtener líderes disponibles excluyendo un grupo específico | Líderes existen, grupo específico existe. | 1. Login como Admin<br>2. Realizar GET a /users/lideres-disponibles?excludeGrupoId=1 | Respuesta 200 OK con líderes disponibles excluyendo el líder del grupo especificado. | P2 | API | RF-94 | Tester |
| Gestión de Usuarios, Roles y Permisos | TC-USU-012 | Acceso restringido: Integrante intenta acceder a ruta de Admin | Usuario Integrante autenticado. | 1. Login como Integrante<br>2. Intentar acceder manualmente a /matriculas | Redirección o mensaje de acceso denegado, funcionalidad no accesible. | P1 | Seguridad | RF-10 | Tester |
| Gestión de Usuarios, Roles y Permisos | TC-USU-013 | Acceso restringido: Líder intenta acceder a ruta de Admin | Usuario Líder autenticado. | 1. Login como Líder<br>2. Intentar acceder manualmente a /matriculas | Redirección o mensaje de acceso denegado, funcionalidad no accesible. | P1 | Seguridad | RF-10 | Tester |
| Gestión de Usuarios, Roles y Permisos | TC-USU-014 | Acceso restringido: Admin intenta acceder a ruta de SuperAdmin | Usuario Admin autenticado. | 1. Login como Admin<br>2. Intentar acceder manualmente a /superadmin | Redirección o mensaje de acceso denegado. | P1 | Seguridad | RF-10 | Tester |
| Gestión de Matrículas | TC-MAT-001 | Listar todas las matrículas | Matrículas existen en BD. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas<br>3. Verificar lista | Tabla muestra todas las matrículas con columnas: código, nombre, programa, período, estado. | P1 | Funcional | RF-12 | Tester |
| Gestión de Matrículas | TC-MAT-002 | Obtener matrícula por ID | Matrícula con ID existe. Usuario Admin autenticado. | 1. Login como Admin<br>2. Realizar GET a /matriculas/{id} | Respuesta 200 OK con MatriculaDTO completo. | P2 | API | RF-12 | Tester |
| Gestión de Matrículas | TC-MAT-003 | Buscar matrículas por código de estudiante | Matrículas con código existen. Usuario Admin autenticado. | 1. Login como Admin<br>2. Realizar GET a /matriculas/estudiante/{codigo} | Respuesta 200 OK con lista de MatriculaDTO del estudiante. | P1 | API | RF-14 | Tester |
| Gestión de Matrículas | TC-MAT-004 | Filtrar matrículas por sede | Matrículas de diferentes sedes existen. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas<br>3. Seleccionar filtro "Sede"<br>4. Seleccionar sede específica<br>5. Aplicar filtro | Solo se muestran matrículas de la sede seleccionada. | P1 | Funcional | RF-13 | Tester |
| Gestión de Matrículas | TC-MAT-005 | Filtrar matrículas por facultad | Matrículas de diferentes facultades existen. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas<br>3. Seleccionar filtro "Facultad"<br>4. Aplicar filtro | Solo se muestran matrículas de la facultad seleccionada. | P1 | Funcional | RF-13 | Tester |
| Gestión de Matrículas | TC-MAT-006 | Filtrar matrículas por programa | Matrículas de diferentes programas existen. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas<br>3. Seleccionar filtro "Programa"<br>4. Aplicar filtro | Solo se muestran matrículas del programa seleccionado. | P1 | Funcional | RF-13 | Tester |
| Gestión de Matrículas | TC-MAT-007 | Filtrar matrículas por período | Matrículas de diferentes períodos existen. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas<br>3. Seleccionar filtro "Período"<br>4. Aplicar filtro | Solo se muestran matrículas del período seleccionado. | P1 | Funcional | RF-13 | Tester |
| Gestión de Matrículas | TC-MAT-008 | Filtrar matrículas por tipo de persona (ESTUDIANTE/INVITADO) | Matrículas de ambos tipos existen. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas<br>3. Seleccionar filtro "Tipo Persona: ESTUDIANTE"<br>4. Aplicar filtro | Solo se muestran matrículas de tipo ESTUDIANTE. | P1 | Funcional | RF-13 | Tester |
| Gestión de Matrículas | TC-MAT-009 | Filtrar matrículas con múltiples criterios combinados | Matrículas con diferentes combinaciones existen. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas<br>3. Seleccionar múltiples filtros: Sede + Facultad + Programa + Período<br>4. Aplicar filtros | Solo se muestran matrículas que cumplen TODOS los criterios seleccionados. | P1 | Funcional | RF-13 | Tester |
| Gestión de Matrículas | TC-MAT-010 | Crear nueva matrícula con datos válidos | Sede, Facultad, Programa, Período y Persona existen. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas<br>3. Click en "Nueva Matrícula"<br>4. Completar formulario con datos válidos<br>5. Click en "Guardar" | Matrícula creada en BD, mensaje de éxito, matrícula visible en lista. | P1 | Funcional | RF-12 | Tester |
| Gestión de Matrículas | TC-MAT-011 | Actualizar matrícula existente | Matrícula existe. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas<br>3. Seleccionar matrícula<br>4. Click en "Editar"<br>5. Modificar datos<br>6. Click en "Guardar" | Matrícula actualizada en BD, cambios reflejados en lista. | P1 | Funcional | RF-12 | Tester |
| Gestión de Matrículas | TC-MAT-012 | Eliminar matrícula | Matrícula existe. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas<br>3. Seleccionar matrícula<br>4. Click en "Eliminar"<br>5. Confirmar eliminación | Matrícula eliminada de BD, mensaje de éxito, matrícula desaparece de lista. | P1 | Funcional | RF-12 | Tester |
| Gestión de Matrículas | TC-MAT-013 | Importar matrículas desde Excel con archivo válido | Archivo Excel válido con formato correcto. Período seleccionado. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas/importar<br>3. Seleccionar período<br>4. Seleccionar archivo Excel válido<br>5. Click en "Importar" | Procesamiento exitoso, reporte muestra: total registros, exitosos, fallidos. Matrículas creadas en BD. | P1 | Funcional | RF-15, RF-17, RF-18 | Tester |
| Gestión de Matrículas | TC-MAT-014 | Importar matrículas con período seleccionado | Archivo Excel válido. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas/importar<br>3. Seleccionar período "2025-I"<br>4. Seleccionar archivo<br>5. Click en "Importar" | Importación exitosa, todas las matrículas asociadas al período seleccionado. | P1 | Funcional | RF-15, RF-17 | Tester |
| Gestión de Matrículas | TC-MAT-015 | Importar matrículas con filtros aplicados (sede, facultad, programa) | Archivo Excel válido. Filtros seleccionados. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas/importar<br>3. Seleccionar período, sede, facultad, programa<br>4. Seleccionar archivo<br>5. Click en "Importar" | Importación exitosa, solo se procesan registros que cumplen los filtros, reporte incluye advertencia de filtros aplicados. | P1 | Funcional | RF-15, RF-18 | Tester |
| Gestión de Matrículas | TC-MAT-016 | Importar matrículas falla con archivo no Excel | Archivo .txt o .pdf. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas/importar<br>3. Seleccionar archivo .txt<br>4. Click en "Importar" | Mensaje de error "El archivo debe ser un Excel (.xlsx o .xls)", importación no procesada. | P1 | Validación | RF-16, RNF-18 | Tester |
| Gestión de Matrículas | TC-MAT-017 | Importar matrículas falla sin seleccionar período | Archivo Excel válido. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas/importar<br>3. NO seleccionar período<br>4. Seleccionar archivo<br>5. Click en "Importar" | Mensaje de error "Debe seleccionar un periodo para la importación", importación no procesada. | P1 | Validación | RF-17 | Tester |
| Gestión de Matrículas | TC-MAT-018 | Importar matrículas falla con archivo vacío | Archivo Excel vacío. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas/importar<br>3. Seleccionar archivo Excel vacío<br>4. Click en "Importar" | Mensaje de error "El archivo está vacío", importación no procesada. | P1 | Validación | RF-16 | Tester |
| Gestión de Matrículas | TC-MAT-019 | Importar matrículas reporta total, exitosos y fallidos | Archivo Excel con algunos registros válidos e inválidos. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas/importar<br>3. Seleccionar archivo con errores<br>4. Click en "Importar" | Reporte muestra: total registros procesados, cantidad exitosos, cantidad fallidos, lista de errores específicos por registro. | P1 | Funcional | RF-18 | Tester |
| Gestión de Matrículas | TC-MAT-020 | Exportar matrículas a Excel sin filtros | Matrículas existen. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas/importar<br>3. Click en "Exportar a Excel" | Descarga de archivo Excel, archivo contiene todas las matrículas, formato válido. | P1 | Funcional | RF-19 | Tester |
| Gestión de Matrículas | TC-MAT-021 | Exportar matrículas a Excel con filtros aplicados | Matrículas existen. Filtros aplicados. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas<br>3. Aplicar filtros (sede, facultad, programa, período)<br>4. Click en "Exportar" | Descarga de archivo Excel, archivo contiene solo matrículas que cumplen los filtros. | P1 | Funcional | RF-19 | Tester |
| Gestión de Matrículas | TC-MAT-022 | Descargar plantilla Excel para importación | Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /matriculas/importar<br>3. Click en "Descargar Plantilla" | Descarga de archivo "Plantilla_Importacion_Matriculas.xlsx", plantilla con columnas correctas y formato válido. | P1 | Funcional | RF-20 | Tester |
| Gestión de Matrículas | TC-MAT-023 | Validar formato de archivo Excel descargado | Archivo Excel descargado. | 1. Descargar plantilla o exportación<br>2. Abrir archivo en Excel o herramienta compatible | Archivo se abre correctamente, columnas visibles, formato válido, datos correctos si es exportación. | P2 | Validación | RF-20, RF-19 | Tester |
| Gestión de Estructura Académica - Sedes | TC-SED-001 | Listar todas las sedes | Sedes existen. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /sedes<br>3. Verificar lista | Tabla muestra todas las sedes con columnas: ID, nombre, descripción. | P1 | Funcional | RF-21 | Tester |
| Gestión de Estructura Académica - Sedes | TC-SED-002 | Obtener sede por ID | Sede con ID existe. Usuario Admin autenticado. | 1. Login como Admin<br>2. Realizar GET a /sedes/{id} | Respuesta 200 OK con SedeDTO completo. | P2 | API | RF-21 | Tester |
| Gestión de Estructura Académica - Sedes | TC-SED-003 | Crear nueva sede con datos válidos | No existe sede con mismo nombre. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /sedes<br>3. Click en "Nueva Sede"<br>4. Ingresar nombre y descripción<br>5. Click en "Guardar" | Sede creada en BD, mensaje de éxito, sede visible en lista. | P1 | Funcional | RF-21, RF-22 | Tester |
| Gestión de Estructura Académica - Sedes | TC-SED-004 | Crear sede falla con nombre duplicado | Sede con mismo nombre ya existe. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /sedes<br>3. Intentar crear sede con nombre existente<br>4. Click en "Guardar" | Mensaje de error de constraint violation, sede no creada. | P1 | Validación/BD | RF-22 | Tester |
| Gestión de Estructura Académica - Sedes | TC-SED-005 | Actualizar sede existente | Sede existe. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /sedes<br>3. Seleccionar sede<br>4. Click en "Editar"<br>5. Modificar datos<br>6. Click en "Guardar" | Sede actualizada en BD, cambios reflejados en lista. | P1 | Funcional | RF-21 | Tester |
| Gestión de Estructura Académica - Sedes | TC-SED-006 | Eliminar sede | Sede existe sin matrículas asociadas. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /sedes<br>3. Seleccionar sede<br>4. Click en "Eliminar"<br>5. Confirmar | Sede eliminada de BD, mensaje de éxito. | P1 | Funcional | RF-21 | Tester |
| Gestión de Estructura Académica - Sedes | TC-SED-007 | Eliminar sede falla si tiene matrículas asociadas | Sede tiene matrículas asociadas. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /sedes<br>3. Intentar eliminar sede con matrículas<br>4. Confirmar | Error de constraint violation, sede no eliminada, mensaje descriptivo. | P1 | BD/Integridad | RNF-11 | Tester |
| Gestión de Estructura Académica - Facultades | TC-FAC-001 | Listar todas las facultades | Facultades existen. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /facultades<br>3. Verificar lista | Tabla muestra todas las facultades con columnas: ID, nombre, descripción. | P1 | Funcional | RF-23 | Tester |
| Gestión de Estructura Académica - Facultades | TC-FAC-002 | Obtener facultad por ID | Facultad con ID existe. Usuario Admin autenticado. | 1. Login como Admin<br>2. Realizar GET a /facultades/{id} | Respuesta 200 OK con FacultadDTO completo. | P2 | API | RF-23 | Tester |
| Gestión de Estructura Académica - Facultades | TC-FAC-003 | Crear nueva facultad con datos válidos | No existe facultad con mismo nombre. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /facultades<br>3. Click en "Nueva Facultad"<br>4. Ingresar nombre y descripción<br>5. Click en "Guardar" | Facultad creada en BD, mensaje de éxito, facultad visible en lista. | P1 | Funcional | RF-23, RF-24 | Tester |
| Gestión de Estructura Académica - Facultades | TC-FAC-004 | Crear facultad falla con nombre duplicado | Facultad con mismo nombre ya existe. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /facultades<br>3. Intentar crear facultad con nombre existente<br>4. Click en "Guardar" | Mensaje de error de constraint violation, facultad no creada. | P1 | Validación/BD | RF-24 | Tester |
| Gestión de Estructura Académica - Facultades | TC-FAC-005 | Actualizar facultad existente | Facultad existe. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /facultades<br>3. Seleccionar facultad<br>4. Click en "Editar"<br>5. Modificar datos<br>6. Click en "Guardar" | Facultad actualizada en BD, cambios reflejados en lista. | P1 | Funcional | RF-23 | Tester |
| Gestión de Estructura Académica - Facultades | TC-FAC-006 | Eliminar facultad | Facultad existe sin programas asociados. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /facultades<br>3. Seleccionar facultad<br>4. Click en "Eliminar"<br>5. Confirmar | Facultad eliminada de BD, mensaje de éxito. | P1 | Funcional | RF-23 | Tester |
| Gestión de Estructura Académica - Facultades | TC-FAC-007 | Eliminar facultad falla si tiene programas asociados | Facultad tiene programas asociados. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /facultades<br>3. Intentar eliminar facultad con programas<br>4. Confirmar | Error de constraint violation, facultad no eliminada. | P1 | BD/Integridad | RNF-11 | Tester |
| Gestión de Estructura Académica - Programas | TC-PRO-001 | Listar todos los programas de estudio | Programas existen. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /programas<br>3. Verificar lista | Tabla muestra todos los programas con columnas: ID, nombre, facultad, descripción. | P1 | Funcional | RF-25 | Tester |
| Gestión de Estructura Académica - Programas | TC-PRO-002 | Obtener programa por ID | Programa con ID existe. Usuario Admin autenticado. | 1. Login como Admin<br>2. Realizar GET a /programas/{id} | Respuesta 200 OK con ProgramaEstudioDTO completo. | P2 | API | RF-25 | Tester |
| Gestión de Estructura Académica - Programas | TC-PRO-003 | Crear nuevo programa con facultad válida | Facultad existe. No existe programa con mismo nombre. Usuario Admin autenticado. | 1. Login como Admin<br>2. Acceder a /programas<br>3. Click en "Nuevo Programa"<br>4. Seleccionar facultad<br>5. Ingresar nombre y descripción<br>6. Click en "Guardar" | Programa creado e
