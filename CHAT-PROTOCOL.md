# Protocolo de Comunicación Entre Chats - Horario Maquita

**Versión:** 1.0  
**Última actualización:** 28/03/2026 - 16:45 UTC  
**Estado:** ✅ ACTIVO

---

## 📌 **ROLES Y NOMBRES DE CHATS**

### Chat 1: "DISEÑO-HORARIO-MAQUITA"
```
Responsabilidad:     Diseño y planificación
Acciones:            Proponer cambios, documentar decisiones
Comando inicial:     Leer PROJECT-CONTEXT.md + CHAT-PROTOCOL.md
Actualiza:           PROJECT-CONTEXT.md (sección "Próximos Pasos")
Git commits:         "design: [descripción]"
Ejemplo:             "design: proponer módulo de calificaciones"
```

### Chat 2: "IMPLEMENTACIÓN-HORARIO-MAQUITA"
```
Responsabilidad:     Codificación y despliegue
Acciones:            Implementar cambios en código, hacer git push
Comando inicial:     Leer PROJECT-CONTEXT.md + CHAT-PROTOCOL.md
Actualiza:           PROJECT-CONTEXT.md (sección "Historial de Cambios")
Git commits:         "feat: [descripción]" o "fix: [descripción]"
Ejemplo:             "feat: agregar módulo de calificaciones en index.html"
Deploy:              Automático (Netlify redeploy 30-60 seg)
```

### Chat 3: "TESTING-HORARIO-MAQUITA"
```
Responsabilidad:     Testing y QA
Acciones:            Probar cambios en vivo, reportar bugs
Comando inicial:     Leer PROJECT-CONTEXT.md + CHAT-PROTOCOL.md
Actualiza:           PROJECT-CONTEXT.md (sección "Bugs Conocidos")
Git commits:         "test: [descripción]" o "docs: [reportes]"
Ejemplo:             "test: validar módulo de calificaciones"
```

---

## 🔄 **FLUJO DE COMUNICACIÓN**

```
┌─────────────────────────────────────────────────────────────────┐
│                    CICLO COMPLETO DE TRABAJO                    │
└─────────────────────────────────────────────────────────────────┘

1️⃣ DISEÑO (Chat 1)
   ├─ Lee PROJECT-CONTEXT.md
   ├─ Propone cambio: "Agregar módulo X"
   ├─ Documenta en PROJECT-CONTEXT.md
   ├─ Commit: "design: plan para módulo X"
   └─ Git push

        ↓ [GitHub actualiza]

2️⃣ IMPLEMENTACIÓN (Chat 2)
   ├─ Lee PROJECT-CONTEXT.md
   ├─ Ve la propuesta de Chat 1
   ├─ Implementa en index.html
   ├─ Commit: "feat: implementar módulo X"
   ├─ Git push
   └─ ✅ NETLIFY REDEPLOY AUTOMÁTICO

        ↓ [30-60 segundos]

3️⃣ TESTING (Chat 3)
   ├─ Lee PROJECT-CONTEXT.md
   ├─ Ve que Chat 2 hizo deployment
   ├─ Prueba en https://horariomaquita.netlify.app
   ├─ Reporta bugs si existen
   ├─ Actualiza PROJECT-CONTEXT.md
   ├─ Commit: "test: validación módulo X"
   └─ Git push

        ↓ [Ciclo completo]

4️⃣ VUELTA A DISEÑO (Chat 1)
   └─ Lee PROJECT-CONTEXT.md con feedback de Testing
      └─ Propone iteración siguiente
```

---

## 📋 **COMANDO INICIAL PARA CADA CHAT**

### **PARA CHAT 1 (DISEÑO):**
```markdown
Acabo de crear un protocolo de comunicación para los 3 chats del proyecto.

Lee estos archivos:
1. PROJECT-CONTEXT.md - Estado actual del proyecto
2. CHAT-PROTOCOL.md - Este archivo

Tu rol: DISEÑADOR
- Propones cambios
- Documentas decisiones
- Actualizas PROJECT-CONTEXT.md
- Haces commits con prefijo "design:"

Ejemplo de flujo:
1. Lees PROJECT-CONTEXT.md
2. Dices: "Propongo agregar módulo X porque..."
3. Yo actualizo PROJECT-CONTEXT.md
4. Hace commit: "design: proponer módulo X"
5. Git push
6. Chat 2 (IMPLEMENTACIÓN) lee el cambio y continúa

¿Entendido? Empecemos.
```

### **PARA CHAT 2 (IMPLEMENTACIÓN):**
```markdown
Acabo de crear un protocolo de comunicación para los 3 chats del proyecto.

Lee estos archivos:
1. PROJECT-CONTEXT.md - Estado actual del proyecto
2. CHAT-PROTOCOL.md - Este archivo

Tu rol: IMPLEMENTADOR
- Lees las propuestas de Chat 1
- Implementas cambios en index.html
- Haces git push (deploy automático a Netlify)
- Actualizas PROJECT-CONTEXT.md con cambios realizados
- Haces commits con prefijo "feat:" o "fix:"

Tu superpoder: Git push automático
- GitHub PAT está configurado
- Netlify redeploy automático (30-60 seg)
- SIN intervención manual

Cuando hagas cambios:
1. Lee PROJECT-CONTEXT.md para contexto
2. Implementa en index.html
3. git add . && git commit -m "feat: descripción"
4. git push → AUTOMÁTICO A NETLIFY
5. Chat 3 lo prueba en vivo

¿Entendido? Te pasaré los cambios.
```

### **PARA CHAT 3 (TESTING):**
```markdown
Acabo de crear un protocolo de comunicación para los 3 chats del proyecto.

Lee estos archivos:
1. PROJECT-CONTEXT.md - Estado actual del proyecto
2. CHAT-PROTOCOL.md - Este archivo

Tu rol: TESTER/QA
- Pruebas cambios en https://horariomaquita.netlify.app
- Reportas bugs encontrados
- Actualizas PROJECT-CONTEXT.md con hallazgos
- Haces commits con prefijo "test:"

Workflow:
1. Chat 2 hace git push
2. Netlify redeploy automático (30-60 seg)
3. Tú pruebas en vivo
4. Reportas bugs o aprobación
5. Actualiza PROJECT-CONTEXT.md

¿Entendido? Chat 2 te avisará cuando hay cambios.
```

---

## 📝 **SECCIONES A ACTUALIZAR EN PROJECT-CONTEXT.md**

### **Chat 1 actualiza:**
```markdown
## 🎯 **PRÓXIMOS PASOS PLANIFICADOS (FASE 2)**

### Módulos Nuevos (Propuestos)
- 🔲 Módulo X: Descripción breve
  - Por qué: Justificación
  - Impacto: Estimación
  - Status: En diseño
```

### **Chat 2 actualiza:**
```markdown
## 📝 **HISTORIAL DE CAMBIOS (v1.0)**

| Fecha | Hora | Chat | Commit | Descripción | Status |
|-------|------|------|--------|-------------|--------|
| 28/03 | 16:45 | IMPLEMENTACIÓN | xyz123 | feat: agregar módulo X | ✅ LIVE |
```

### **Chat 3 actualiza:**
```markdown
## 🐛 **BUGS CONOCIDOS Y REPORTES DE TESTING**

| Fecha | Bug | Criticidad | Status | Chat |
|-------|-----|-----------|--------|------|
| 28/03 | X no funciona en móvil | 🔴 Alta | Abierto | TESTING |
```

---

## 🔐 **REGLAS DE ORO**

### ✅ **DEBES HACER:**
1. Leer PROJECT-CONTEXT.md PRIMERO
2. Actualizar PROJECT-CONTEXT.md DESPUÉS de cada acción
3. Commits significativos (con prefijo correcto)
4. Git push sin miedo (deploy automático)
5. Comunicar cambios en el archivo de contexto

### ❌ **NO DEBES HACER:**
1. Cambiar index.html sin documento de diseño
2. Olvidar git push
3. No actualizar PROJECT-CONTEXT.md
4. Commits genéricos ("fix bug", "update")
5. Asumir que los otros chats saben qué hiciste

---

## 🚀 **EJEMPLO COMPLETO: Agregar Módulo de Calificaciones**

### **CHAT 1 (DISEÑO):**
```
"Propongo agregar módulo de calificaciones con:
- Vista de notas por evaluación
- Cálculo automático de promedio
- Seguimiento visual (barras de progreso)"

Yo actualizo PROJECT-CONTEXT.md:
  - Sección "Próximos Pasos": Marca como "En diseño"
  - Sección "Decisiones": Documenta arquitectura
  
Commit: "design: proponer módulo de calificaciones"
Git push
```

### **CHAT 2 (IMPLEMENTACIÓN):**
```
Lee PROJECT-CONTEXT.md → Ve la propuesta

"Implementando módulo de calificaciones en index.html:
- Agregué sección HTML
- Agregué CSS para estilos
- Agregué JavaScript para lógica"

Actualiza PROJECT-CONTEXT.md:
  - "Historial de Cambios": Nuevo commit
  - "Estado General": Versión incrementada

Commit: "feat: agregar módulo de calificaciones"
Git push → NETLIFY REDEPLOY AUTOMÁTICO
```

### **CHAT 3 (TESTING):**
```
Lee PROJECT-CONTEXT.md → Ve deployment en Netlify

"Probando módulo de calificaciones en:
https://horariomaquita.netlify.app

✅ Funciona en desktop
⚠️ Bug: En móvil no calcula promedio
✅ Estilos responsivos"

Actualiza PROJECT-CONTEXT.md:
  - "Bugs Conocidos": Documenta el bug en móvil

Commit: "test: reporte módulo de calificaciones"
Git push
```

### **CHAT 1 (DISEÑO) - ITERACIÓN:**
```
Lee PROJECT-CONTEXT.md → Ve bug reportado

"Chat 3 encontró bug en móvil. Propongo fix:
- Revisar función de cálculo en localStorage
- Validar parseFloat() en números"

Actualiza PROJECT-CONTEXT.md con propuesta

Commit: "design: fix propuesto para bug móvil"
Git push → Chat 2 implementa...
```

---

## 📞 **RESUMEN RÁPIDO**

| Elemento | Valor |
|----------|-------|
| **Chat 1 Nombre** | DISEÑO-HORARIO-MAQUITA |
| **Chat 2 Nombre** | IMPLEMENTACIÓN-HORARIO-MAQUITA |
| **Chat 3 Nombre** | TESTING-HORARIO-MAQUITA |
| **Archivo de contexto** | PROJECT-CONTEXT.md |
| **Protocolo de comunicación** | CHAT-PROTOCOL.md (este archivo) |
| **Deploy automático** | SÍ (Netlify) |
| **Intervención manual** | NO |
| **Tiempo de deploy** | 30-60 segundos |

---

**FIN DEL PROTOCOLO**  
Última actualización: 28/03/2026 - 16:45 UTC
