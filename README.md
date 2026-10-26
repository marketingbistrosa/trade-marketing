# Trade Marketing · DeliDips

Página de trade marketing para Kyros, Salsas Kansas y Kansas Bakery. Incluye cuentas, dinámicas, calendario de promociones, clipping, precio sugerido de venta y competencia.

**100% gratuita:**
- La página se publica en **GitHub Pages**, gratis.
- Los datos se guardan en **Firebase**, en el plan gratuito *Spark*, sin tarjeta.
- Los precios y promos se cargan **a mano** con la Carga rápida.

Con una cuenta de Google, todo el equipo ve lo mismo en vivo.

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La página. |
| `config.js` | Datos de tu proyecto de Firebase. **Es lo único que hay que completar.** |
| `firestore.rules` | Quién puede entrar y cargar datos. |
| `datos-iniciales.json` | Todo lo cargado hasta ahora. Se importa una sola vez. |

---

## Paso 1 · Crear el proyecto en Firebase (gratis, ≈10 min)

1. Entrá a <https://console.firebase.google.com> y tocá **Crear un proyecto**. Ponele un nombre, por ejemplo `trade-marketing-delidips`. Google Analytics no hace falta.
2. **Base de datos:** **Compilación → Firestore Database → Crear base de datos**. Elegí **modo de producción** y la ubicación `southamerica-east1` (San Pablo).
3. **Ingreso con Google:** **Compilación → Authentication → Comenzar → Google → Habilitar → Guardar**.
4. **App web:** **⚙ Configuración del proyecto → Tus apps → ícono `</>`**. Ponele un nombre y registrala. Copiá los valores de `firebaseConfig` en `config.js`.

> El proyecto queda en el plan **Spark (gratuito)**. No cambies a Blaze: no hace falta.

## Paso 2 · Definir quién tiene acceso

1. Abrí `firestore.rules` y reemplazá `persona1@gmail.com`, `persona2@gmail.com` por los mails del equipo. Si todos tienen mail de la empresa, podés habilitar el dominio completo en la línea comentada.
2. En Firebase: **Firestore Database → Reglas**. Pegá el contenido completo del archivo y tocá **Publicar**.

Para sumar o sacar a alguien más adelante, editá la lista y volvé a publicar.

## Paso 3 · Publicar en GitHub Pages (gratis, ≈5 min)

1. En <https://github.com> creá un repositorio nuevo, por ejemplo `trade-marketing`.
2. Tocá **Add file → Upload files** y subí todos los archivos.
3. Entrá a **Settings → Pages**. Elegí **Deploy from a branch**, rama `main`, carpeta `/ (root)`, y tocá **Save**.
4. En uno o dos minutos la página queda en `https://TU-USUARIO.github.io/trade-marketing/`.
5. **Importante:** en Firebase, entrá a **Authentication → Settings → Authorized domains → Add domain** y agregá `TU-USUARIO.github.io`.

## Paso 4 · Importar lo que ya estaba cargado (una sola vez)

Entrá a la página con tu cuenta de Google, tocá **⚙ Configuración → Importar datos** y elegí `datos-iniciales.json`.

Desde **⚙ Configuración** también se puede **descargar un respaldo** completo cuando quieran. Conviene hacerlo una vez por mes.

---

## Cómo se carga un relevamiento

1. **Clipping** → elegí la cadena → **⚡ Cargar relevamiento**.
2. Aparece la lista de todos los productos Kyros y Kansas. Completá **solo lo que ves**:
   - **Precio de lista.** Con el botón de "Última carga" de cada fila, o con **↺ Usar últimos precios de lista**, se copia el precio anterior.
   - **Promo.** Elegila de la lista (10% OFF, 20% OFF, 2x1, 2da al 70%…) o escribila.
   - **Precio con promo.** Si la promo es un %, se calcula solo. Si cargás el precio con promo, el % se calcula solo.
3. Con **Enter** pasás a la fila de abajo, como en Excel.
4. Las secciones **Marca blanca** y **Competencia** son opcionales y se abren tocándolas.
5. **📎 Adjuntar captura** (opcional) muestra la imagen al lado mientras cargás y queda como respaldo durante 2 meses.
6. **Guardar relevamiento.** Los precios pasan solos a **Precio sugerido de venta** y **Competencia**.

Para corregir algo: **Editar datos** en el relevamiento.

## Límites del plan gratuito

El plan Spark permite **1 GB de datos** y **50.000 lecturas por día**, de sobra para el uso del equipo. Las miniaturas de las capturas se borran solas a los 2 meses para no ocupar espacio.

## Preguntas frecuentes

- **"Tu cuenta todavía no tiene acceso":** ese mail no está en `firestore.rules`. Agregalo y publicá las reglas de nuevo.
- **No se abre la ventana de Google:** falta agregar `TU-USUARIO.github.io` en *Authorized domains* (paso 3.5).
- **¿Es seguro que `config.js` esté en GitHub?** Sí. Los datos de Firebase de una app web son públicos por diseño; lo que protege la información son las reglas del paso 2.
