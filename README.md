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
Acceso completo al sistema incluyendo:
- Gestión de usuarios (agregar, eliminar, cambiar roles)
- Reportes y estadísticas
- Configuración del sistema y modo mantenimiento
- Backup manual
- Historial de cambios por registro
- Eliminación de registros en todas las secciones
- Contabilidad completa

### 👤 Usuario
Acceso operativo incluyendo:
- Carga y edición de solicitudes
- Gestoría, Prendas, Gestores, Clientes, Concesionarias
- Sistema de créditos
- Bancos (accesos rápidos)
- Mi cuenta

---

## 📋 Secciones del sistema

### 🏠 Inicio — Solicitudes
Tabla principal con todas las solicitudes de crédito. Incluye:
- Paginación (20 registros por página)
- Filtros por estado, banco, concesionaria, provincia, usuario y fechas
- Buscador por nombre, DNI, banco, dominio
- Stats clickeables (Total, Aprobados, Rechazados, Avanza)
- Exportación a Excel y PDF
- Panel lateral al hacer clic en un registro
- Auto-refresh cada 1 minuto

### 📊 Reportes *(solo admin)*
- Gráfico de torta por estados
- Barras de registros por mes
- Barras de Comisión LUKAYA por mes con filtro de fechas

### 📁 Gestoría
Gestión de asignación de gestores a las solicitudes.

### 📌 Prendas
Seguimiento del estado prendario de cada operación (En proceso / Presentada / Finalizada).

### ✅ Prendas entregadas *(admin en topbar)*
Operaciones con fecha de finalización registrada.

### 👤 Gestores
ABM de gestores con datos de contacto, dirección y código postal. Buscador incluido.

### 🧑 Clientes
Registro automático de clientes desde las solicitudes. Datos de contacto editables.

### 🏢 Concesionarias
Registro automático de concesionarias desde las solicitudes. Incluye CUIT, contacto, ubicación, historial de cambios y acceso a Google Maps.

### 🧾 Contabilidad *(admin y usuario)*
Tres solapas:
- **💰 Liquidaciones:** tabla con cálculos automáticos por solicitud AVANZA. Filtros por fecha y buscador. Campos calculados: 1,2 Imp. Crédito, Comisión LUKAYA, Comisión Gestor, Retribución Banco, Ganancia LUKAYA, A Liquidar Agencia.
- **📊 Totales:** sumatorias del período filtrado.
- **⚙️ Cambio de Coeficientes:** permite modificar los porcentajes usados en los cálculos desde el sistema sin tocar el código.

### 💳 Sistema de créditos
Seguimiento de créditos prendarios otorgados. Permite:
- Vincular un crédito a una solicitud AVANZA
- Definir cantidad de cuotas y fecha de inicio
- Visualizar el avance automático mes a mes (cuota 1 de 12, 2 de 12, etc.)
- Enviar recordatorio de vencimiento de cuota por WhatsApp con mensaje personalizado

### 🏦 Bancos
Accesos rápidos a portales bancarios (Banco Columbia). Abre en nueva pestaña.

### 👥 Usuarios *(solo admin)*
- Alta, eliminación y cambio de rol de usuarios
- Indicador de conexión en tiempo real (● Conectado / ○ Desconectado)
- Contador de solicitudes cargadas por usuario

---

## 🔧 Configuración *(solo admin)*

### URL del Apps Script
Desde **Configuración** en el menú lateral se puede actualizar la URL del backend.

### Modo mantenimiento
Permite activar una pantalla de mantenimiento para usuarios mientras el admin sigue operando con normalidad.

---

## 💾 Backup *(solo admin)*
Descarga manual de una copia de la planilla en formato Excel.

---

## 📊 Google Sheets — Estructura

El sistema utiliza un único Google Sheet con las siguientes pestañas:

| Pestaña | Contenido |
|---|---|
| Solicitudes | Registros principales (31 columnas) |
| Usuarios | Credenciales y roles |
| Listas | Valores de los desplegables |
| Historial | Auditoría de cambios por registro |
| Gestores | Datos de gestores |
| Gestoría | Registros asignados |
| Prendas | Estado prendario |
| Clientes | Datos de contacto de clientes |
| Concesionarias | Datos de concesionarias |
| Contabilidad | Datos contables por operación |
| Creditos | Créditos prendarios |
| Cuotas | Cuotas generadas por crédito |
| Config | Configuración del sistema (coeficientes, mantenimiento, heartbeats) |

---

## 🔄 Procedimiento de actualización

### Solo HTML (sin cambios en el backend):
1. Modificar `index.html`
2. Subir a GitHub
3. En el navegador: `Ctrl + F5`

### HTML + Apps Script:
1. Pegar el código en el editor de Google Apps Script
2. Guardar con `Ctrl + S`
3. Implementar → Nueva implementación → Ejecutar como: **Yo** / Acceso: **Cualquier usuario**
4. Copiar la nueva URL y pegarla en el campo correspondiente dentro del sistema (Configuración) o actualizar en el `index.html`
5. Subir `index.html` a GitHub

---

## 📦 Archivos del proyecto

```
index.html        → Frontend completo del sistema
apps-script.js    → Backend (pegar en Google Apps Script)
README.md         → Este archivo
```

---

## 📝 Notas importantes

- El sistema usa **GitHub Pages** para el hosting, por lo que puede haber caché. Si no se ven los cambios, usar `Ctrl + F5` o abrir en modo incógnito.
- La velocidad del sistema depende de **Google Apps Script**, que puede tener demoras de algunos segundos especialmente en el primer uso del día (cold start).
- Los datos se sincronizan automáticamente con Google Sheets en cada acción.
- El auto-refresh se ejecuta cada **1 minuto** para mantener los datos actualizados entre usuarios.
