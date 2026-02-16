# 🎤 Beni Pla - Website de Stand-Up Comedy

Website profesional para Beni Pla, comediante español de stand-up comedy en Miami.

## 🌟 Características

- **Diseño Neón Nocturno**: Estética de club nocturno con colores azul y rojo neón
- **Integración con Google Sheets**: Los shows se cargan automáticamente desde tu hoja de cálculo
- **Panel de Administración**: Edita contenido sin tocar código
- **Subida de Imágenes a GitHub**: Sube fotos directamente desde el panel admin
- **Carrusel de Reels**: Muestra tus mejores reels de Instagram
- **Optimizado para SEO y LLMs**: Schema.org, Open Graph, y metadatos para AI
- **Responsive**: Se ve perfecto en móvil, tablet y desktop
- **Formulario de Contacto**: Para contrataciones y consultas

## 📁 Estructura del Proyecto

```
benipla-web/
├── index.html          # Página principal
├── llms.txt           # Información para LLMs
├── robots.txt         # Configuración para buscadores
├── README.md          # Este archivo
└── assets/
    └── images/
        ├── beni-hero.jpg      # Imagen principal del hero
        ├── beni-about.jpg     # Imagen de la sección "Sobre mí"
        ├── beni-og-image.jpg  # Imagen para redes sociales
        ├── favicon.png        # Favicon del sitio
        └── reels/             # Miniaturas de reels
```

## 🚀 Instalación

### Opción 1: GitHub Pages (Recomendado)

1. Crea un repositorio en GitHub llamado `benipla.github.io` o `tu-usuario.github.io`
2. Sube todos los archivos a la rama `main`
3. Ve a Settings > Pages > Source: `main` branch
4. Tu web estará disponible en `https://tu-usuario.github.io`

### Opción 2: WordPress

1. Instala el plugin "WPCode" o "Code Snippets"
2. Crea una nueva página en WordPress
3. Usa el editor de código (HTML) y pega todo el contenido de `index.html`
4. Alternativamente, usa un plugin de "Custom HTML Page" para cargar el archivo completo

### Opción 3: Hosting propio

1. Sube los archivos a tu servidor vía FTP
2. Asegúrate de que `index.html` esté en la raíz del dominio

## ⚙️ Configuración

### Google Sheets para Shows

1. Tu hoja de cálculo debe tener estas columnas:
   - `fecha` o `date`: Fecha del show (formato: YYYY-MM-DD)
   - `ciudad` o `city`: Nombre de la ciudad
   - `recinto` o `venue`: Nombre del lugar
   - `tickets` o `link`: URL para comprar entradas

2. Publica la hoja:
   - Ve a Archivo > Compartir > Publicar en la web
   - Selecciona "Documento completo" y "Página web"
   - Copia el ID de la URL (la parte entre `/d/` y `/edit`)

3. Actualiza el ID en `index.html`:
   ```javascript
   GOOGLE_SHEET_ID: 'tu-id-aqui',
   ```

### Panel de Administración

1. Haz clic en el icono de rueda dentada (⚙️) en el footer
2. Credenciales por defecto:
   - Usuario: `admin`
   - Contraseña: `benipla2025`

3. **¡IMPORTANTE!** Cambia las credenciales en `index.html`:
   ```javascript
   ADMIN_USER: 'tu-usuario',
   ADMIN_PASS: 'tu-contraseña-segura',
   ```

### Subir Imágenes a GitHub

1. Ve al panel de administración > pestaña "Imágenes"
2. Necesitas un Personal Access Token de GitHub:
   - Ve a GitHub > Settings > Developer settings > Personal access tokens
   - Genera un nuevo token con permiso `repo`
3. Introduce el token y el nombre de tu repositorio (ej: `benipla/benipla-web`)
4. Arrastra o selecciona imágenes para subirlas

## 🎨 Personalización

### Colores

Edita las variables CSS en `:root`:

```css
:root {
    --neon-blue: #00d4ff;      /* Azul neón principal */
    --neon-pink: #ff006e;      /* Rosa neón */
    --neon-red: #ff1744;       /* Rojo para botones */
    --deep-purple: #1a0a2e;    /* Fondo degradado */
    --midnight: #0a0a0f;       /* Fondo principal */
}
```

### Fuentes

El sitio usa Google Fonts:
- **Bebas Neue**: Para títulos
- **Outfit**: Para texto general

### Contenido

Todo el contenido se puede editar desde el panel de administración:
- Frase de impacto (Hero)
- Biografía completa
- Estadísticas
- Videos de YouTube
- Reels de Instagram
- Enlaces a redes sociales

## 📱 Redes Sociales

Configura tus enlaces desde el panel admin o editando directamente en `CONFIG.defaults.social`:

```javascript
social: {
    instagram: 'https://instagram.com/benipla',
    tiktok: 'https://tiktok.com/@benipla',
    youtube: 'https://youtube.com/@benipla',
    facebook: 'https://facebook.com/benipla'
}
```

## 🔍 SEO y LLMs

El sitio incluye:
- Meta tags optimizados
- Open Graph para redes sociales
- Schema.org markup (JSON-LD)
- Archivo `llms.txt` para AI crawlers
- Metadata embebida para LLMs

## 📧 Formulario de Contacto

El formulario de contacto genera un email usando `mailto:`. Para cambiar el email de destino, busca y reemplaza:

```javascript
window.location.href = `mailto:contacto@benipla.com?...`
```

## 🐛 Solución de Problemas

### Los shows no cargan
- Verifica que la hoja de Google Sheets esté publicada
- Comprueba que el ID del sheet sea correcto
- Asegúrate de que las columnas tengan los nombres correctos

### Las imágenes no se suben
- Verifica tu Personal Access Token de GitHub
- Asegúrate de que el token tenga permisos `repo`
- Comprueba que el formato del repositorio sea `usuario/repo`

### El panel admin no abre
- Limpia la caché del navegador
- Verifica las credenciales

## 📄 Licencia

© 2025 Beni Pla. Todos los derechos reservados.

---

**¿Preguntas?** Contacta en contacto@benipla.com 
