# 🎓 Horario Macarena

Aplicación web de horario académico para Macarena Arriagada · Ing. Civil Biomédica (2026).

**URL Viva:** https://horariomaquita.netlify.app

## ✨ Características

- 📱 **Totalmente responsivo** - Funciona en desktop, tablet y móvil
- 🚀 **PWA** - Instala como app nativa en tu teléfono
- 📲 **Notificaciones** - Alertas 15 min, 5 min antes de clase
- 📝 **Notas por clase** - Agrega tareas y recordatorios
- 📊 **Estadísticas** - Ve tu carga académica semanal
- 🌙 **Dark mode** - Ajusta automáticamente al tema del sistema
- 📤 **Exportar** - Descarga como .ics o HTML

## 🛠️ Estructura

```
horario-macarena/
├── index.html          # App completa (single-file)
├── .gitignore         # Archivos a ignorar
├── README.md          # Este archivo
└── .netlify/          # Config de deploy (auto)
```

## 🚀 Desarrollo Local

1. **Clonar/Descargar:**
   ```bash
   git clone https://github.com/nico0521/horario-macarena.git
   cd horario-macarena
   ```

2. **Abrir en navegador:**
   ```bash
   # Opción A: Abrir directamente
   open index.html
   
   # Opción B: Servidor local (Python)
   python -m http.server 8000
   # Luego: http://localhost:8000
   ```

## 📝 Editar el Horario

En `index.html`, busca:

```javascript
const RAMOS = {
  mat:{name:'Matemática',color:'#7F77DD',...},
  // Agrega/edita ramos aquí
};

const SCHEDULE = {
  1:[{start:[11,10],end:[12,25],ramo:'fis',...}],
  // Edita horarios por día (1=Lunes, 5=Viernes)
};
```

## 🌐 Deploy en Netlify

El proyecto está configurado para:
1. **Auto-deploy** cada push a `main`
2. **Build instantáneo** (no necesita compilación)
3. **Staging automático** en PRs

### Variables de entorno
Sin necesidad de configuración adicional.

### Build command
```
(ninguno - archivo estático)
```

### Publish directory
```
/
```

## 🔄 Workflow (GitHub + Netlify)

```
Tu código (GitHub) → Push → Netlify (automático) → Sitio online
```

1. Haz cambios locales
2. `git add .` y `git commit`
3. `git push origin main`
4. Netlify despliega automáticamente ✨

## 📱 Instalar como App

### iOS
1. Safari → Compartir → Agregar a pantalla principal
2. ¡Listo! Abre desde el ícono

### Android
1. Chrome → Menú → "Instalar aplicación"
2. Elige dónde (Home, etc.)

## 🤝 Contribuir

Para mejoras o cambios:
1. Crea una rama: `git checkout -b feature/mi-mejora`
2. Haz commits: `git commit -m "Descrición"`
3. Push: `git push origin feature/mi-mejora`
4. Abre PR

## 📄 Licencia

Libre para uso personal. Créditos a Macarena Arriagada 💜

---

**Última actualización:** Marzo 2026
**Mantenedor:** @nico0521
