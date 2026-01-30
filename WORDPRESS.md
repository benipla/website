# Guía de Integración con WordPress

## Método 1: Página HTML Personalizada (Recomendado)

### Usando el plugin "Custom HTML Page"

1. Instala el plugin "Custom HTML Page" desde WordPress
2. Ve a "Custom HTML Pages" > "Add New"
3. Copia todo el contenido de `index.html`
4. Pega en el editor
5. Configura el permalink (ej: `/home` o `/`)
6. Publica

### Usando WPCode (Code Snippets)

1. Instala "WPCode – Insert Headers and Footers + Custom Code Snippets"
2. Ve a Code Snippets > Add Snippet
3. Selecciona "Custom HTML"
4. Copia todo el contenido de `index.html`
5. Configura para ejecutar en todas las páginas o en una específica

## Método 2: Tema Hijo con Template Personalizado

1. Crea un tema hijo de tu tema actual
2. Crea un archivo `page-comedy.php` con este contenido:

```php
<?php
/*
Template Name: Beni Pla Landing
*/

// Obtener el contenido del archivo HTML
get_header();
?>
<!DOCTYPE html>
<html lang="es">
<!-- Pega aquí todo el contenido de index.html -->
</html>
<?php
// No incluir footer de WordPress
exit;
?>
```

3. En WordPress, crea una nueva página
4. En "Atributos de página", selecciona "Beni Pla Landing"
5. Publica

## Método 3: Subdirectorio

1. Sube la carpeta `benipla-web` a `/wp-content/`
2. Accede via `tudominio.com/wp-content/benipla-web/`
3. Configura una redirección en `.htaccess`:

```apache
RewriteEngine On
RewriteRule ^comedy$ /wp-content/benipla-web/index.html [L]
```

## Notas Importantes

### Conflictos con Estilos de WordPress

El CSS de la landing está encapsulado, pero si hay conflictos:

1. Añade `!important` a los estilos problemáticos
2. O envuelve todo en un contenedor con ID único:
   ```css
   #benipla-landing * {
       /* tus estilos */
   }
   ```

### Google Sheets

La integración con Google Sheets funciona igual independientemente de dónde hospedes el sitio. Solo asegúrate de que la hoja esté publicada públicamente.

### Imágenes

Las imágenes deben estar en una ubicación accesible:
- Usa la biblioteca de medios de WordPress
- O sube a GitHub y usa las URLs absolutas
- O coloca en `/wp-content/uploads/benipla/`

### SSL/HTTPS

Asegúrate de que:
- Tu WordPress use HTTPS
- Los enlaces a Google Sheets usen HTTPS
- Las imágenes se carguen desde HTTPS

## Soporte

Si tienes problemas con la integración, revisa:
1. La consola del navegador (F12) para errores JavaScript
2. Que todas las URLs sean correctas
3. Que Google Sheets esté correctamente publicado
