# UGeVi Development

Sitio estático bilingüe para el repositorio independiente ugevi-development-site. Las políticas siguen en borrador. No subir esta versión.

- index.html y en/index.html son los inicios.
- products/ y en/products/ alojan las fichas.
- privacy/ y en/privacy/ alojan las políticas.
- assets/ contiene CSS e ícono compartidos.
- .nojekyll permite servir los archivos estáticos sin procesarlos con Jekyll.

Para ver el sitio en local, abrir index.html o ejecutar python -m http.server 8765 --bind 127.0.0.1 desde esta carpeta.

## Antes de autorizar la publicación

1. Confirmar la identidad de la persona responsable del tratamiento, el domicilio que corresponda en Argentina y la fecha de vigencia. El correo público y de privacidad es ugevidevelopment@gmail.com.
2. Validar las decisiones comerciales sobre jugadores de 13 a 17 años y de edad desconocida, y confirmar por mercado la configuración de UMP y AdMob. Comprobar el manifiesto fusionado del binario comercial y reflejar los datos, usos, conservación y opciones efectivos en ambos idiomas y en Seguridad de los datos.
3. Revisar ambos textos definitivos, retirar los avisos de borrador y pedir autorización expresa para crear el repositorio público y hacer push. El repositorio local se mantiene separado del juego.

## Completar los datos en privado

Editar privacy/lumen-sort.html (Quién es responsable) y en/privacy/lumen-sort.html (Who is responsible). Reemplazar en cada página los tres marcadores: [COMPLETAR_NOMBRE_LEGAL], [COMPLETAR_DOMICILIO_LEGAL] y [COMPLETAR_FECHA_VIGENCIA]. Mantener el mismo nombre, domicilio y fecha efectiva en ambos idiomas, con el formato de fecha que corresponda. Argentina ya está indicado.

La Ley argentina 25.326, artículo 6 inciso b, prevé informar la identidad y el domicilio del responsable cuando corresponde su deber de información. Confirmar antes de publicar si puede utilizarse un domicilio de contacto o profesional válido para el caso concreto. No asumir que se debe publicar el domicilio particular ni que alcanza con un correo. Revisar también el alcance en los mercados de lanzamiento. No compartir los datos en el chat.

Para verificar desde PowerShell, parado en la carpeta del sitio:

```powershell
Select-String -LiteralPath privacy/lumen-sort.html,en/privacy/lumen-sort.html -Pattern '\[COMPLETAR_[A-Z_]+\]' -List
```

El comando debe quedar sin resultados. Abrir ambos HTML localmente, verificar que los datos se vean completos, que coincidan y que el enlace de correo funcione. Si algún dato contiene un ampersand o signos de menor/mayor, usar entidades HTML como &amp;, &lt; y &gt; al editar. No retirar el aviso de borrador ni noindex hasta validar el texto completo y la configuración publicitaria real. GitHub Pages publica el HTML y el repositorio público expone su historial. Revisar el contenido antes de subirlo.

## Activación después de la autorización

1. Renovar la sesión con gh auth login -h github.com y completar el flujo en el navegador. Comprobar el propietario con gh api user --jq .login. Si no coincide con la cuenta confirmada, detenerse. No copiar credenciales al chat ni al proyecto.
2. Consultar de forma autenticada si existe PROPIETARIO/ugevi-development-site, incluidos repositorios privados. Si existe o la respuesta es inconcluyente, detenerse. Verificar además que la raíz Git sea esta carpeta, que no haya remoto y que los únicos archivos preparados sean los del sitio.
3. Solo tras aprobación expresa del contenido público, crear el repositorio público nuevo PROPIETARIO/ugevi-development-site sin hacer push en el mismo paso. Consultar su propietario, nombre y URL HTTPS en GitHub. Agregar esa URL exacta como origin de este repositorio local y comprobar git remote get-url --push origin antes de subir main. Si cualquier dato difiere, detenerse. No reutilizar, renombrar ni modificar un repositorio existente.
4. En el repositorio nuevo, elegir Settings → Pages → Deploy from a branch, rama main y carpeta / (root). Activar Enforce HTTPS cuando esté disponible.
5. Comprobar las seis páginas desde una ventana privada sin iniciar sesión. Conservar el propietario, nombre del repositorio y las rutas para mantener estables los enlaces.

Patrones de URL, todavía sin verificar públicamente

- Español: https://PROPIETARIO.github.io/ugevi-development-site/privacy/lumen-sort.html
- Inglés: https://PROPIETARIO.github.io/ugevi-development-site/en/privacy/lumen-sort.html

Una vez publicadas y verificadas, enlazar la política desde la app y Play Console. Comprobar que se abra sin iniciar sesión, sin restricciones geográficas y como HTML. Revisar app-ads.txt por separado. Un sitio de proyecto vive bajo /ugevi-development-site/ y no sirve ese archivo en la raíz del host.

## Referencias

- https://www.argentina.gob.ar/normativa/nacional/ley-25326-64790/actualizacion
- https://support.google.com/googleplay/android-developer/answer/9859455
- https://support.google.com/googleplay/android-developer/answer/10787469
- https://developers.google.com/admob/android/privacy/play-data-disclosure
- https://developers.google.com/admob/flutter/privacy
- https://developers.google.com/admob/flutter/targeting
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https
