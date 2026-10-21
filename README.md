# Mi Dinero — prototipo PWA para iPhone

## Incluye
- Resumen mensual y anual (2024–2032)
- Ingresos y gastos con fecha, categoría, notas y estado pendiente/cobrado/pagado
- Edición y eliminación de movimientos
- Saldo inicial por mes, cierre mensual y arrastre del saldo previsto al mes siguiente
- Registro de deudas y abonos
- Objetivos de ahorro y aportaciones
- Exportación anual CSV y copia/restauración JSON
- Carga inicial de los datos de octubre de 2026
- Preparación para sincronización privada con Supabase

## Importante sobre la persistencia
El prototipo guarda datos localmente en el navegador hasta que se configure la nube. El almacenamiento del navegador puede perderse si se borran los datos del sitio. Descarga copias JSON periódicas.
La sincronización Supabase es una copia de seguridad del estado completo de la app, no sincronización multiusuario en tiempo real. Usa una sola cuenta personal.

## Publicar y añadir a pantalla de inicio
1. Sube todos los archivos de esta carpeta a un alojamiento estático HTTPS (por ejemplo, GitHub Pages o Netlify).
2. Abre la URL publicada en Safari en el iPhone.
3. Pulsa Compartir → Añadir a pantalla de inicio.
4. Abre el icono Mi Dinero.

## Activar la nube privada con Supabase
1. Crea un proyecto en Supabase.
2. En Authentication, crea un usuario con tu correo y contraseña. Desactiva el registro público si aparece activado; la cuenta debe ser privada.
3. En SQL Editor, ejecuta el contenido de `SETUP_SUPABASE.sql`.
4. En Project Settings → API, copia Project URL y la clave pública anon/publishable. No uses `service_role` ni ninguna clave secreta.
5. En la app, entra en Ajustes y copias, introduce URL, clave pública y correo, guarda la configuración, escribe la contraseña y pulsa Iniciar sesión.
6. Pulsa Sincronizar copia. La primera sincronización sube los datos locales. Si ya existe una copia en nube, podrás elegir restaurarla o reemplazarla con la copia local.

## Limitaciones del prototipo
- No es asesoramiento financiero ni conexión bancaria.
- El cierre guarda una fotografía del saldo previsto; reabrir permite corregirlo.
- La primera versión mantiene movimientos en un único estado local y la nube guarda una copia del conjunto. No ofrece resolución avanzada de conflictos entre varios dispositivos.
- Antes de introducir datos muy sensibles, valida la configuración de autenticación, RLS y copias de seguridad.
Actualización de publicación.
