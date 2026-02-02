# Guía de Despliegue en Netlify

## 📋 Requisitos Previos

- Cuenta en GitHub
- Cuenta en Netlify (gratis en [netlify.com](https://www.netlify.com/))
- Tu proyecto subido a GitHub

## 🚀 Pasos para Desplegar

### 1. Subir tu Proyecto a GitHub

```bash
# Inicializa git si no lo has hecho
git init

# Añade todos los archivos
git add .

# Haz tu primer commit
git commit -m "Initial commit: GP Web Studio website"

# Conecta con tu repositorio de GitHub
git remote add origin https://github.com/TU-USUARIO/GP-web-studio.git

# Sube los archivos
git push -u origin main
```

### 2. Conectar con Netlify

1. Ve a [app.netlify.com](https://app.netlify.com/)
2. Haz clic en **"Add new site"** → **"Import an existing project"**
3. Selecciona **GitHub**
4. Autoriza a Netlify para acceder a tus repositorios
5. Selecciona el repositorio **GP-web-studio**

### 3. Configurar el Deploy

En la pantalla de configuración:

- **Branch to deploy**: `main`
- **Build command**: (dejar vacío)
- **Publish directory**: `.` o dejar vacío
- Haz clic en **"Deploy site"**

### 4. Configuración del Dominio

Una vez desplegado:

- Netlify te dará una URL como: `https://random-name-123.netlify.app`
- Puedes cambiar el nombre en: **Site settings** → **Change site name**
- Sugerencia: `gpwebstudio.netlify.app`

### 5. Configurar Dominio Personalizado (Opcional)

Si tienes un dominio propio:

1. Ve a **Domain settings** → **Add custom domain**
2. Ingresa tu dominio (ej: `gpwebstudio.com`)
3. Sigue las instrucciones para configurar los DNS
4. Netlify proveerá SSL gratis automáticamente

## 📧 Configurar Formularios

### Opción 1: Netlify Forms (Recomendado)

1. En tu `index.html`, modifica el form:
   ```html
   <form
     name="contact"
     method="POST"
     netlify
     netlify-honeypot="bot-field"
   ></form>
   ```
2. Añade un campo oculto:
   ```html
   <input type="hidden" name="form-name" value="contact" />
   ```
3. Los mensajes llegarán a tu email asociado a Netlify

### Opción 2: Formspree

Sigue las instrucciones en `FORMSPREE_SETUP.md`

## 🔄 Actualizaciones Automáticas

Cada vez que hagas push a GitHub, Netlify desplegará automáticamente:

```bash
git add .
git commit -m "Actualización de contenido"
git push
```

## ✅ Verificación Post-Deploy

- [ ] El sitio carga correctamente
- [ ] Todas las secciones son visibles
- [ ] Los enlaces de navegación funcionan
- [ ] El formulario envía mensajes
- [ ] El sitio es responsive en móvil
- [ ] Las imágenes cargan bien

## 🐛 Solución de Problemas

### El sitio no despliega

- Verifica que no haya errores en los archivos
- Revisa los logs en Netlify Dashboard

### Los estilos no se ven

- Verifica que las rutas de CSS sean correctas
- Las rutas deben ser relativas: `css/styles.css`

### El formulario no funciona

- Verifica la configuración de Formspree
- O usa Netlify Forms como alternativa

## 📊 Monitoreo

En Netlify Dashboard puedes ver:

- Cantidad de visitantes
- Envíos de formularios
- Performance del sitio
- Logs de deploy

¡Tu sitio estará en línea en minutos! 🎉
