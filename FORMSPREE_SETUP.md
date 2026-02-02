# Configuración del Formulario de Contacto

## Instrucciones para Formspree

Para que el formulario de contacto funcione correctamente, necesitas configurar Formspree:

### Paso 1: Crear Cuenta en Formspree

1. Ve a [formspree.io](https://formspree.io/)
2. Crea una cuenta gratuita
3. El plan gratuito permite hasta 50 envíos por mes

### Paso 2: Obtener tu Form ID

1. Una vez dentro, crea un nuevo formulario
2. Formspree te dará un ID único que se ve así: `xpznabcd`
3. La URL completa será: `https://formspree.io/f/xpznabcd`

### Paso 3: Actualizar index.html

1. Abre el archivo `index.html`
2. Busca la línea que dice:
   ```html
   <form
     class="contact__form"
     id="contact-form"
     action="https://formspree.io/f/YOUR_FORM_ID"
     method="POST"
   ></form>
   ```
3. Reemplaza `YOUR_FORM_ID` con tu ID real de Formspree

### Ejemplo:

```html
<form
  class="contact__form"
  id="contact-form"
  action="https://formspree.io/f/xpznabcd"
  method="POST"
></form>
```

### Paso 4: Configuración Adicional

En el panel de Formspree puedes configurar:

- Email de destino donde recibirás los mensajes
- Página de confirmación personalizada
- Auto-respuesta al usuario
- Protección anti-spam (reCAPTCHA)

### Alternativa: Email Directo

Si prefieres usar tu propio email sin Formspree:

1. Puedes usar Netlify Forms (gratis con Netlify)
2. Solo añade `netlify` al tag del form:
   ```html
   <form name="contact" netlify></form>
   ```

## Verificación

Una vez configurado:

1. Abre tu sitio web
2. Llena el formulario
3. Envía un mensaje de prueba
4. Verifica que recibiste el email

¡Listo! Tu formulario estará funcionando.
