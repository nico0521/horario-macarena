# Horario Maquita - Contexto del Proyecto

**Última actualización:** 28/03/2026 - 16:15 UTC  
**Versión actual:** v1.0 (Backup seguro creado)

---

## 📌 **ESTADO GENERAL DEL PROYECTO**

### Versión y Respaldos
- **Versión activa:** v1.0 (Estable)
- **Backup de seguridad:** `v1.0-backup-before-major-refactor` (GitHub Tag)
- **Commit actual:** `c93eb4e` (fix: mostrar clases vacias en fin de semana)
- **Status:** ✅ FUNCIONAL - Listo para refactorización

### Descripción General
App de gestión de horarios académicos para Macarena Arriagada (Ing. Civil Biomédica, 1er Semestre 2026).
- **Plataforma:** Web Single-Page Application (SPA) - 100% HTML/CSS/JS
- **Ubicación:** https://horariomaquita.netlify.app
- **Almacenamiento:** localStorage (navegador)
- **Responsividad:** Mobile-first, responsive design

---

## 🏗️ **ARQUITECTURA TÉCNICA**

### Stack Tecnológico

```
Frontend:
├─ HTML5 (estructura)
├─ CSS3 (estilos + dark mode automático)
├─ JavaScript Vanilla (sin frameworks)
└─ Service Worker (PWA offline)

Datos:
├─ localStorage (clases, ramos, notas)
└─ JSON (serialización)

Despliegue:
├─ GitHub (control de versiones)
├─ Netlify (CI/CD automático)
└─ Domain: horariomaquita.netlify.app
```

### Estructura de Archivos del Proyecto
```
horario-macarena/
├─ index.html (726 líneas - app completa)
├─ .gitignore
├─ README.md (118 líneas)
└─ PROJECT-CONTEXT.md (este archivo)
```

### Flujo de CI/CD

```
Usuario/Claude edita index.html
    ↓
git add . && git commit && git push
    ↓
GitHub webhook dispara
    ↓
Netlify detecta cambio
    ↓
Build automático (instantáneo)
    ↓
Deploy a: https://horariomaquita.netlify.app
    ↓
Disponible en: 30-60 segundos
    ↓
Usuario actualiza página (F5) → VER CAMBIOS EN VIVO
```

### Autenticación y Permisos

| Servicio | Configurado | Estado |
|----------|------------|--------|
| **GitHub PAT** | Sí (github_pat_11BDLFBXQ0...) | ✅ Activo |
| **Netlify Site ID** | `06ed6a28-28be-4ec2-980c-72cde9af41e` | ✅ Vinculado |
| **Git Credential Helper** | Sí (Windows + Linux) | ✅ Automático |
| **Netlify Auto-Deploy** | Habilitado | ✅ Activo |

---

## 📊 **CARACTERÍSTICAS IMPLEMENTADAS (v1.0)**

### Dashboard
- ✅ Próxima clase en tiempo real
- ✅ Contador de clases hoy
- ✅ Barra de progreso del día
- ✅ Indicadores visuales de estado

### Horario
- ✅ Vista semanal (Lunes-Viernes)
- ✅ Detalles: hora, profesor, sala, NRC
- ✅ Tabs por día con indicador "hoy"
- ✅ Clases en curso resaltadas

### Ramos
- ✅ 6 asignaturas completas
- ✅ Estadísticas: bloques, horas, días
- ✅ Progreso visual por ramo
- ✅ Información de profesor y NRC

### Estadísticas
- ✅ Horas semanales por ramo
- ✅ Carga por día (gráfico)
- ✅ Resumen semanal (totales)
- ✅ Día más cargado destacado

### Sistema de Notas
- ✅ Agregar nota por clase
- ✅ Persistencia en localStorage
- ✅ Edición y eliminación
- ✅ Vista inline en lista de clases

### Compartir
- ✅ Exportar a Google Calendar (iCal)
- ✅ Copiar enlace al portapapeles
- ✅ Descargar HTML offline
- ✅ Compartir nativo (navegador)

### Notificaciones
- ✅ Permisos solicitados al iniciar
- ✅ Alertas 15 min antes de clase
- ✅ Alertas 5 min antes de clase
- ✅ Información de sala incluida

### Interfaz
- ✅ Responsive mobile-first
- ✅ Dark mode automático
- ✅ Animaciones suaves (CSS)
- ✅ Navegación inferior (bottom nav)
- ✅ PWA instalable

---

## 🐛 **BUGS CORREGIDOS (v1.0)**

### Bug #1: Mapeo incorrecto de días de semana
- **Problema:** `getDay()` devuelve 0-6, código esperaba 1-5. Sábado se mapeaba a Lunes.
- **Síntoma:** En fin de semana mostraba clases de lunes
- **Solución:** Validación `if(dow>=1&&dow<=5)` antes de acceder a SCHEDULE
- **Commit:** `0b4ecc4`

### Bug #2: Botón de test de notificaciones roto
- **Problema:** Botón visible pero no funcionaba
- **Síntoma:** Al hacer clic no pasaba nada
- **Solución:** Eliminar botón completamente (no necesario en producción)
- **Commit:** `0b4ecc4`

### Bug #3: Clases mostradas en fin de semana
- **Problema:** Dashboard decía "sin clases" pero abajo mostraba clases de lunes
- **Síntoma:** Contradictorio en sábado/domingo
- **Solución:** Pasar `dow` directamente a `renderDayList()` sin cambiar a 1
- **Commit:** `c93eb4e`

---

## 📈 **DATOS ACADÉMICOS (SCHEDULE)**

### Horario Base Macarena (Semestre 2026-1)

**Lunes (1):**
- 11:10-12:25: Intro a la Física (B404, Piso 4 Amberes Sur)
- 12:30-13:45: Intro a la Física (B404, Piso 4 Amberes Sur)
- 15:10-16:25: Intro Ing. Biomédica (P208, Piso 2 Post Grado)
- 16:30-17:45: Intro Ing. Biomédica (P208, Piso 2 Post Grado)

**Martes (2):**
- 08:30-09:45: Matemática (A706, Piso 7 Amberes Norte)
- 13:50-15:05: Matemática (P208, Piso 2 Post Grado)
- 15:10-16:25: Matemática (P305, Piso 3 Post Grado) [Reserva]

**Miércoles (3):**
- 08:30-09:45: Química General (B204, Piso 2 Amberes Sur)
- 09:50-11:05: Química General (B204, Piso 2 Amberes Sur)
- 12:30-13:45: Matemática (B301, Piso 3 Amberes Sur)
- 13:50-15:05: Taller Pens. Comuni. Arte (P308, Piso 3 Post Grado)
- 15:10-16:25: Taller Pens. Comuni. Arte (P308, Piso 3 Post Grado)

**Jueves (4):**
- 11:10-12:25: Intro a la Física (Por confirmar)
- 12:30-13:45: Intro a la Física (Por confirmar) [R]

**Viernes (5):**
- 08:30-09:45: Química General (Por confirmar)
- 09:50-11:05: Química General (Por confirmar) [R]
- 15:10-16:25: Antropología FT (B405, Piso 4 Amberes Sur)
- 16:30-17:45: Antropología FT (B405, Piso 4 Amberes Sur)

### Ramos Inscritos (6)
| Código | Ramo | Profesor | NRC | Bloques/sem | Horas/sem |
|--------|------|----------|-----|-------------|-----------|
| MAT | Matemática | Marcela Rojas Carvajal | 21597 | 3 | 3.75h |
| QUI | Química General | Alejandra Tapia Castillo | 23752/24095 | 4 | 5h |
| FIS | Intro a la Física | Diego Teca Wellmann | 21596/21599 | 4 | 5h |
| TAL | Taller Pens. Comuni. Arte | Pedro Salas Camus | 11132 | 2 | 2.5h |
| ANT | Antropología (FT) | Pablo Maillet Aranguiz | 23941 | 2 | 2.5h |
| BIO | Intro Ing. Biomédica | Juan Ignacio Spinetto | 21595 | 2 | 2.5h |

---

## 🔐 **ACCESO Y CONFIGURACIÓN**

### GitHub
- **Repository:** https://github.com/nico0521/horario-macarena
- **Owner:** nico0521
- **Email:** calderon.rn@hotmail.com
- **PAT configurado:** SÍ (almacenado en `.git-credentials`)
- **Rama:** `main` (protegida)

### Netlify
- **Site Name:** horariomaquita
- **Site ID:** 06ed6a28-28be-4ec2-980c-72cde9af41e
- **URL:** https://horariomaquita.netlify.app
- **Build:** Automático en cada push
- **Tiempo de deploy:** 30-60 segundos

### Control de Cambios (MCP)
- **Herramienta:** Claude con Desktop Commander + GitHub
- **Capacidad:** Editar, commit, push automático
- **Flujo:** Editar → commit → push → deploy automático
- **Sin intervención manual necesaria:** ✅ Totalmente automatizado

---

## 📝 **HISTORIAL DE CAMBIOS (v1.0)**

| Fecha | Hora | Commit | Descripción | Autor |
|-------|------|--------|-------------|-------|
| 28/03 | 16:15 | c93eb4e | Fix: mostrar clases vacías en fin de semana | Claude |
| 28/03 | 15:45 | 0b4ecc4 | Fix: corregir lógica de días de semana | Claude |
| 28/03 | 15:30 | 4a06a80 | Feat: agregar botón test notificaciones | Claude |
| [Anterior] | - | - | Versión inicial | Inicial |

---

## 🎯 **PRÓXIMOS PASOS PLANIFICADOS (FASE 2)**

### Módulos Nuevos (A definir en nuevo chat)
- 🔲 **Módulo Calificaciones:** Tracking de notas por evaluación
- 🔲 **Módulo Asistencia:** Registro de asistencia por clase
- 🔲 **Módulo Tareas:** Pendientes relacionadas a clases
- 🔲 **Módulo Material:** Apuntes, links, recursos
- 🔲 **Dashboard Unificado:** Integración de todos los módulos

### Mejoras de Arquitectura
- 🔲 Benchmarking de apps similares
- 🔲 Decisión: Mantener SPA o migrar a framework
- 🔲 Decisión: Mantener localStorage o usar backend
- 🔲 Diseño de nueva estructura de datos
- 🔲 Integración de diseños Google Stitch

---

## 💡 **DECISIONES ARQUITECTÓNICAS TOMADAS**

### ¿Por qué single-file HTML?
✅ **Ventajas:**
- Distribución simple (un solo archivo)
- Deploy instantáneo (Netlify automático)
- PWA sin complejidad adicional
- Sin dependencias externas
- Fácil de iterar

⚠️ **Limitaciones:**
- Crecimiento limitado de complejidad
- Mantenimiento difícil si crece mucho
- Sin separación de concerns clara

**Decisión:** Viable para v1.0, pero refactorización necesaria si se agregan múltiples módulos.

### ¿Por qué localStorage?
✅ **Ventajas:**
- Persistencia sin backend
- Privacidad (datos del usuario)
- Funciona offline
- Implementación simple

⚠️ **Limitaciones:**
- Límite ~5-10MB
- No sincroniza entre dispositivos
- Sin backup en nube

**Decisión:** Suficiente para v1.0. Posible migración a Netlify DB en futuro.

### ¿Por qué Netlify?
✅ **Ventajas:**
- Deploy automático desde GitHub
- HTTPS por defecto
- CDN global
- Interfaz amigable
- Gratuito con opciones pagadas

**Decisión:** Plataforma óptima para este proyecto.

---

## 📞 **CONTACTO Y REFERENCIAS**

- **Usuario:** Macarena Arriagada
- **Carrera:** Ing. Civil Biomédica
- **Semestre:** 1er Semestre 2026
- **Universidad:** (No especificada en datos)
- **Proyecto lead:** nico0521 (GitHub)

---

## 📋 **NOTAS PARA OTROS CHATS**

> Si accedes a este archivo desde otro chat, tendrás:
> 1. ✅ Estado actual del proyecto
> 2. ✅ Historial de cambios y commits
> 3. ✅ Acceso a GitHub PAT para deploy
> 4. ✅ Entendimiento de arquitectura
> 5. ✅ Decisiones ya tomadas

**Para hacer cambios desde tu chat:**
- Lee este archivo primero para contexto
- Haz cambios al código (index.html)
- Actualiza este archivo con los cambios
- Git push automático (PAT configurado)
- Netlify redeploy (automático)

---

**FIN DEL DOCUMENTO**  
Última actualización: 28/03/2026 - 16:15 UTC
