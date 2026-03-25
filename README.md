# 🚗 Grupo Olyar — Sistema de Gestión de Solicitudes

Sistema web para la gestión de solicitudes de crédito prendario automotor. Permite registrar, hacer seguimiento y administrar todas las operaciones desde una interfaz centralizada.

---

## 🌐 Acceso

**URL del sistema:** [https://tolcese.github.io/grupo-olyar-solicitudes](https://tolcese.github.io/grupo-olyar-solicitudes)

---

## 🛠️ Tecnologías

| Componente | Tecnología |
|---|---|
| Frontend | HTML / CSS / JavaScript (archivo único) |
| Hosting | GitHub Pages |
| Base de datos | Google Sheets |
| Backend | Google Apps Script |

---

## 👥 Roles y permisos

### ⚡ Admin
- Gestión de usuarios (agregar, eliminar, cambiar roles, ver estado de conexión)
- Reportes y estadísticas
- Configuración del sistema y modo mantenimiento
- Backup manual
- Historial de cambios por registro
- Eliminación de registros en todas las secciones
- Contabilidad completa
- Edición de créditos en Sistema de créditos

### 👤 Usuario
- Carga y edición de solicitudes
- Gestoría, Prendas, Gestores, Clientes, Concesionarias
- Sistema de créditos (ver y crear)
- Datero (ver respuestas del formulario)
- Bancos (accesos rápidos)
- Mi cuenta

---

## 📋 Secciones del sistema

### 🏠 Inicio — Solicitudes
Tabla principal con todas las solicitudes. Incluye paginación (20 por página), filtros, buscador, stats clickeables, exportación a Excel/PDF, panel lateral, auto-refresh cada 1 minuto. Al editar y guardar vuelve a la misma página. Estado obligatorio al cargar solicitud nueva.

### 📊 Reportes *(solo admin)*
Torta por estados, barras por mes, Comisión LUKAYA por mes con filtro de fechas.

### 📁 Gestoría
Asignación de gestores a solicitudes. Buscador de gestor al asignar.

### 📌 Prendas
Seguimiento del estado prendario (En proceso / Presentada / Finalizada).

### ✅ Prendas entregadas *(admin en topbar)*
Operaciones finalizadas. Incluye columna "Fecha entregada" editable.

### 👤 Gestores
ABM de gestores con datos de contacto, dirección y C.P. Buscador incluido.

### 🧑 Clientes
Registro automático desde solicitudes. Datos de contacto editables.

### 🏢 Concesionarias
Registro automático desde solicitudes. Incluye CUIT, contacto, ubicación, historial de cambios, acceso a Google Maps y alta manual.

### 📨 Datero
Respuestas en tiempo real del formulario Google (DATERO OPERACIONES). Incluye todos los campos del form, panel lateral, link a foto DNI, buscador y punto rojo 🔴 en topbar cuando llegan respuestas nuevas.

### 🏦 Bancos
Acceso rápido al portal de Banco Columbia (nueva pestaña).

### 🧾 Contabilidad *(admin y usuario)*
- **💰 Liquidaciones:** cálculos automáticos por solicitud AVANZA. Campos: 1.2 Imp. Crédito, Comisión LUKAYA, Comisión Gestor, Retribución Banco, Ganancia LUKAYA, A Liquidar Agencia.
- **📊 Totales:** sumatorias del período filtrado.
- **⚙️ Cambio de Coeficientes:** modificar porcentajes desde el sistema.

### 💳 Sistema de créditos
- **Créditos:** tarjetas con progreso automático mes a mes.
- **Cuotas:** contador cuota actual (ej: 2 de 12) con fecha de vencimiento.
- Panel lateral con botón **💬 WhatsApp** que genera el recordatorio automáticamente.

### 💳 Sistema de créditos — En construcción
Sección reservada para futuras funcionalidades.

### 👥 Usuarios *(solo admin)*
Alta/baja/cambio de rol. Indicador de conexión en tiempo real. Contador de solicitudes por usuario.

---

## 🔧 Configuración *(solo admin)*
- URL del Apps Script
- Modo mantenimiento

---

## 💾 Backup *(solo admin)*
Descarga manual de la planilla en formato Excel.

---

## 📊 Google Sheets — Pestañas

| Pestaña | Contenido |
|---|---|
| Solicitudes | Registros principales (31 columnas) |
| Usuarios | Credenciales y roles |
| Listas | Valores de desplegables |
| Historial | Auditoría de cambios |
| Gestores | Datos de gestores |
| Gestoría | Registros asignados |
| Prendas | Estado prendario |
| Clientes | Datos de contacto |
| Concesionarias | Datos de concesionarias |
| Contabilidad | Datos contables |
| Creditos | Créditos prendarios |
| Cuotas | Cuotas por crédito |
| Config | Coeficientes, mantenimiento, heartbeats |

Sheet externo del Datero: 

---

## 🔄 Actualización

### Solo HTML:
1. Modificar  → subir a GitHub → 

### HTML + Apps Script:
1. Pegar código en Apps Script → 
2. Implementar → Nueva implementación → Ejecutar como: **Yo** / Acceso: **Cualquier usuario**
3. Copiar URL nueva → actualizar en 
4. Subir  a GitHub

---

## 📦 Archivos



---

## 📝 Notas

- Caché de GitHub Pages: usar  o modo incógnito si no se ven cambios.
- Apps Script puede tener demoras en el primer uso del día (cold start).
- Auto-refresh cada **1 minuto**.
- Heartbeat de usuarios cada **30 segundos**, timeout de conexión: **2 minutos**.
- Fotos del DNI en Drive requieren estar logueado con la cuenta con acceso.
