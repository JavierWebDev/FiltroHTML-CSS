# README: Estructura del HTML de CampusShop

Este README proporciona una descripción de la estructura del archivo HTML proporcionado para el proyecto CampusShop. Este archivo HTML es la página principal del sitio web y contiene elementos como la barra lateral, la barra de navegación, y la sección principal donde se muestran los productos.

## Estructura del archivo HTML

El archivo HTML sigue la siguiente estructura:

1. `<!DOCTYPE html>`: Define la versión de HTML utilizada.

2. `<html lang="en">`: Elemento raíz del documento HTML con el atributo de idioma establecido en "en" (inglés).

3. ```
   <head>
   ```

   : Contiene metadatos y enlaces a archivos CSS y JavaScript.

   - Metadatos: Definen el juego de caracteres y la configuración de la vista inicial.
   - Enlaces a archivos externos de estilos CSS y scripts JavaScript.
   - Título de la página.

4. ```
   <body>
   ```

   : Contiene todo el contenido visible de la página.

   - `#sidebar`: Sección de la barra lateral que contiene enlaces a diferentes secciones del sitio.

   - ```
     #content
     ```

     : Sección principal que contiene la barra de navegación y el contenido principal.

     - `nav`: Barra de navegación superior que incluye un icono de menú desplegable y un formulario de búsqueda (actualmente vacío).

     - ```
       main
       ```

       : Contiene el contenido principal de la página.

       - `h1.title`: Título principal de la página.

       - `ul.breadcrumbs`: Lista de migas de pan para navegar por las diferentes secciones del sitio.

       - ```
         section.data
         ```

         : Sección donde se muestran los productos.

         - Tarjetas (

           ```
           div.card
           ```

           ) para cada producto, con su imagen, título y botón para obtener más información.

           - Para cada categoría de productos (abrigos, camisas, pantalones), se muestran tarjetas individuales para cada producto.

# Estilos

```css
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;500;600;700&display=swap');

* {
	font-family: 'Open Sans', sans-serif;
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}

:root {
	--grey: #F1F0F6;
	--dark-grey: #8D8D8D;
	--light: #fff;
	--dark: #000;
	--green: #81D43A;
	--light-green: #E3FFCB;
	--blue: #1775F1;
	--light-blue: #D0E4FF;
	--dark-blue: #0C5FCD;
	--red: #FC3B56;
}

html {
	overflow-x: hidden;
}

body {
	background: var(--grey);
	overflow-x: hidden;
}

a {
	text-decoration: none;
}

li {
	list-style: none;
}

img {
	max-height: 100%;
	max-width: 100%;
}
```

**Estilos generales**

- `*`: Apunta a todos los elementos en la página.
- `font-family`: Establece la fuente en "Open Sans" para todos los elementos.
- `margin`, `padding`: Reinicia los márgenes y rellenos a 0 para todos los elementos.
- `box-sizing`: Asegura que el relleno y el borde estén incluidos en el ancho y alto total del elemento.

- Define varias variables CSS para colores y tonos, facilitando el  mantenimiento y la actualización del esquema de colores del sitio web.

- `html`: Oculta el desbordamiento horizontal para evitar el desplazamiento.
- `body`: Establece el color de fondo en el gris claro definido por la variable `--grey` y oculta el desbordamiento horizontal para evitar el desplazamiento.

- `a`: Elimina los subrayados de las etiquetas de anclaje.
- `li`: Elimina el estilo de lista predeterminado.
- `img`: Asegura que las imágenes no excedan las dimensiones de su contenedor estableciendo una altura y ancho máximo del 100%.

***

```css
/* SIDEBAR */
#sidebar {
	position: fixed;
	max-width: 260px;
	width: 100%;
	background: var(--light);
	top: 0;
	left: 0;
	height: 100%;
	overflow-y: auto;
	scrollbar-width: none;
	transition: all .3s ease;
	z-index: 200;
	overflow: scroll;
}
#sidebar.hide {
	max-width: 60px;
}
#sidebar.hide:hover {
	max-width: 260px;
}
#sidebar::-webkit-scrollbar {
	display: none;
}
#sidebar .brand {
	font-size: 24px;
	display: flex;
	align-items: center;
	height: 64px;
	font-weight: 700;
	color: var(--blue);
	position: sticky;
	top: 0;
	left: 0;
	z-index: 100;
	background: var(--light);
	transition: all .3s ease;
	padding: 0 6px;
}
#sidebar .icon {
	min-width: 48px;
	display: flex;
	justify-content: center;
	align-items: center;
	margin-right: 6px;
}
#sidebar .icon-right {
	margin-left: auto;
	transition: all .3s ease;
}
#sidebar .side-menu {
	margin: 36px 0;
	padding: 0 20px;
	transition: all .3s ease;
}
#sidebar.hide .side-menu {
	padding: 0 6px;
}
#sidebar.hide:hover .side-menu {
	padding: 0 20px;
}
#sidebar .side-menu a {
	display: flex;
	align-items: center;
	font-size: 14px;
	color: var(--dark);
	padding: 12px 16px 12px 0;
	transition: all .3s ease;
	border-radius: 10px;
	margin: 4px 0;
	white-space: nowrap;
}
#sidebar .side-menu > li > a:hover {
	background: var(--grey);
}
#sidebar .side-menu > li > a.active .icon-right {
	transform: rotateZ(90deg);
}
#sidebar .side-menu > li > a.active,
#sidebar .side-menu > li > a.active:hover {
	background: var(--blue);
	color: var(--light);
}
#sidebar .divider {
	margin-top: 24px;
	font-size: 12px;
	text-transform: uppercase;
	font-weight: 700;
	color: var(--dark-grey);
	transition: all .3s ease;
	white-space: nowrap;
}
#sidebar.hide:hover .divider {
	text-align: left;
}
#sidebar.hide .divider {
	text-align: center;
}
#sidebar .side-dropdown {
	padding-left: 54px;
	max-height: 0;
	overflow-y: hidden;
	transition: all .15s ease;
}
#sidebar .side-dropdown.show {
	max-height: 1000px;
}
#sidebar .side-dropdown a:hover {
	color: var(--blue);
}
#sidebar .ads {
	width: 100%;
	padding: 20px;
}
#sidebar.hide .ads {
	display: none;
}
#sidebar.hide:hover .ads {
	display: block;
}
#sidebar .ads .wrapper {
	background: var(--grey);
	padding: 20px;
	border-radius: 10px;
}
#sidebar .btn-upgrade {
	font-size: 14px;
	display: flex;
	justify-content: center;
	align-items: center;
	padding: 12px 0;
	color: var(--light);
	background: var(--blue);
	transition: all .3s ease;
	border-radius: 5px;
	font-weight: 600;
	margin-bottom: 12px;
}
#sidebar .btn-upgrade:hover {
	background: var(--dark-blue);
}
#sidebar .ads .wrapper p {
	font-size: 12px;
	color: var(--dark-grey);
	text-align: center;
}
#sidebar .ads .wrapper p span {
	font-weight: 700;
}
```

#### Estilos Generales de la Barra Lateral

- `#sidebar`: Define los estilos generales para la barra lateral, como posición fija, ancho máximo, color de fondo y transiciones.
- `#sidebar.hide`: Establece los estilos cuando la barra lateral está oculta.
- `#sidebar .brand`: Establece los estilos para el logotipo y el encabezado de la barra lateral.
- `#sidebar .side-menu`: Define los estilos para los elementos del menú lateral, como márgenes, relleno y transiciones.
- `#sidebar .divider`: Define los estilos para las divisiones en el menú lateral.

#### Interactividad y Animaciones

- `#sidebar.hide:hover`: Define los estilos cuando el cursor se desplaza sobre la barra lateral oculta.
- `#sidebar .side-menu > li > a:hover`: Establece los estilos cuando el cursor se desplaza sobre los elementos del menú.
- `#sidebar .side-menu > li > a.active`: Establece los estilos para el elemento de menú activo.
- `#sidebar .side-menu > li > a.active .icon-right`: Define los estilos para el icono en el elemento de menú activo.

#### Elementos Adicionales

- `#sidebar .side-dropdown`: Define los estilos para los menús desplegables dentro de la barra lateral.
- `#sidebar .btn-upgrade`: Define los estilos para el botón de actualización.

***

```css
.card-img__producto1, .card-img__producto2, .card-img__producto3, .card-img__producto4 {
	width: 200px;
	height: 300px;
	background-size: cover;
	background-repeat: no-repeat;
	background-position: center;

	transition: transform 0.2s ease;
}

.card-img__producto1 {
	background-image: url("/FiltroHTML-CSS/CampusShop/img/Sweters/producto1/grande1.webp");
}
.card-img__producto2 {
	background-image: url("/FiltroHTML-CSS/CampusShop/img/Sweters/producto2/grande1.webp");
}
.card-img__producto3 {
	background-image: url("/FiltroHTML-CSS/CampusShop/img/Sweters/producto3/grande1.webp");
}
.card-img__producto4 {
	background-image: url("/FiltroHTML-CSS/CampusShop/img/Sweters/producto4/grande1.webp");
}

.card-img__producto1:hover, .card-img__producto2:hover, .card-img__producto3:hover, .card-img__producto4:hover {
	transform: scale(1.1);
	border: double 5px var(--green);
	border-radius: 10px;
}
```

- `.card-img__producto1, .card-img__producto2, .card-img__producto3, .card-img__producto4`: Estas clases definen el estilo para las imágenes de productos. Cada una representa una imagen de producto específica.
- `width` y `height`: Establecen el ancho y la altura de las imágenes de producto.
- `background-size: cover`: Ajusta la imagen de fondo para cubrir todo el contenedor sin distorsión.
- `background-repeat: no-repeat`: Evita que la imagen de fondo se repita.
- `background-position: center`: Centra la imagen de fondo dentro del contenedor.
- `transition: transform 0.2s ease;`: Aplica una transición suave de 0.2 segundos al efecto de transformación (escala) cuando se produce un cambio.

- `.card-img__producto1`, `.card-img__producto2`, `.card-img__producto3`, `.card-img__producto4`: Cada clase define la imagen de fondo para una tarjeta de producto específica, utilizando una URL diferente.
- `background-image`: Establece la imagen de fondo para la tarjeta de producto utilizando la URL especificada.

- `.card-img__producto1:hover, .card-img__producto2:hover, .card-img__producto3:hover, .card-img__producto4:hover`: Estas reglas definen los estilos que se aplicarán cuando el cursor esté sobre las imágenes de producto.
- `transform: scale(1.1);`: Escala la imagen en un 10% más grande en comparación con su tamaño original cuando el cursor está sobre ella.
- `border: double 5px var(--green);`: Agrega un borde doble de 5px de ancho de color verde alrededor de la imagen.
- `border-radius: 10px;`: Aplica un radio de borde de 10px para redondear las esquinas de la imagen.

***

# Links Utilizados

## ABRIGOS 

https://articulo.mercadolibre.com.co/MCO-1270985375-chaqueta-ovejero-hombre-impermeable-capota-bolsillos-_JM#is_advertising=true&position=1&search_layout=grid&type=pad&tracking_id=cdc8ec37-c238-4739-8595-bad73376ba70&is_advertising=true&ad_domain=VQCATCORE_LST&ad_position=1&ad_click_id=MjU4MDYzMTUtY2I1Ny00NWE4LWJkOWMtMTAxYzQxMjNhNDU0

https://articulo.mercadolibre.com.co/MCO-576870813-chaqueta-buzo-sudadera-algodon-hombre-_JM#position=2&search_layout=grid&type=item&tracking_id=685f726b-5a75-43f4-954e-d70205fd38ab

https://articulo.mercadolibre.com.co/MCO-619853549-calidad-chaqueta-hombre-cuero-sintetico-diseno-ropa-_JM#position=3&search_layout=grid&type=item&tracking_id=af1b07cc-0029-4778-b2de-e9460ae87327

https://articulo.mercadolibre.com.co/MCO-858975933-chaqueta-hombre-acolchada-impermeable-invierno-cuello-alto-abrigo-moda-masculina-liviana-urbana-ropa-de-calle-calidad-premium-_JM#reco_item_pos=6&reco_backend=pads-retrieval-model&reco_backend_type=low_level&reco_client=vip-pads-up&reco_id=7287584f-cdf9-488d-b665-35f62f3851e7&reco_backend_model=pads_retrieval_model&is_advertising=true&ad_domain=VIPDESKTOP_UP&ad_position=7&ad_click_id=ZDY5M2I4Y2UtMzczZS00NzdmLWFmZTUtM2IyMGUxOTA1M2Q1

## CAMISAS

https://articulo.mercadolibre.com.co/MCO-604798900-camisa-corbata-unicolor-slim-fit-_JM#position=4&search_layout=grid&type=item&tracking_id=d0a39165-3441-401c-ae14-bed42d80660b

https://articulo.mercadolibre.com.co/MCO-1523505372-guayabera-blancas-hombres-4-bolsillos-_JM#position=7&search_layout=grid&type=item&tracking_id=5b9324a6-8f3b-4d95-9410-775af6f46495

https://articulo.mercadolibre.com.co/MCO-540337118-camisa-colegial-cuello-corbata-blanca-nino-manga-larga-_JM#position=5&search_layout=grid&type=item&tracking_id=9c044d22-51dd-4d3e-87fc-521cf713b05f

https://articulo.mercadolibre.com.co/MCO-473234325-camisa-oxford-dotacion-empresarial-clasico-_JM#position=16&search_layout=grid&type=item&tracking_id=7dbab354-53d0-4754-bdef-bcfa9aced1fe

## PANTALONES 

https://articulo.mercadolibre.com.co/MCO-561856762-jeans-comfort-negro-para-hombre-_JM#reco_item_pos=0&reco_backend=pads-retrieval-model&reco_backend_type=low_level&reco_client=vip-pads-up&reco_id=762f7098-1225-414d-b25b-73062c98396e&reco_backend_model=pads_retrieval_model&is_advertising=true&ad_domain=VIPDESKTOP_UP&ad_position=1&ad_click_id=Y2MzZDlhMmItYTlkZi00OTEzLWI2NjQtM2E1MmEwNjI3ZDIy

https://articulo.mercadolibre.com.co/MCO-609491789-jean-gris-chaspeado-pantalon-de-caballero-diseno-exclusivo-_JM#reco_item_pos=5&reco_backend=pads-retrieval-model&reco_backend_type=low_level&reco_client=vip-pads-up&reco_id=ddbea689-e624-4da9-94cc-ac767cd0bcb1&reco_backend_model=pads_retrieval_model&is_advertising=true&ad_domain=VIPDESKTOP_UP&ad_position=6&ad_click_id=NjZhMGI2MGEtOWRlZC00YzkxLWI1ZWUtZjZkMjFjMWExNTg4

https://articulo.mercadolibre.com.co/MCO-1290446453-jean-de-disenador-exclusivo-de-alta-calidad-en-tela-licrada-_JM#reco_item_pos=6&reco_backend=pads-retrieval-model&reco_backend_type=low_level&reco_client=vip-pads-up&reco_id=5d784a06-8f46-43f1-a41d-b3b936a3e0e9&reco_backend_model=pads_retrieval_model&is_advertising=true&ad_domain=VIPDESKTOP_UP&ad_position=7&ad_click_id=MjY1ODYwYmEtZGY0OS00YTZkLWIzMDgtMDI0MjBjZWI2ODdm

https://articulo.mercadolibre.com.co/MCO-600617518-pantalon-de-hombre-_JM#reco_item_pos=10&reco_backend=pads-retrieval-model&reco_backend_type=low_level&reco_client=vip-pads-up&reco_id=5fbd18a4-241c-4471-a4bb-81820054cdfe&reco_backend_model=pads_retrieval_model&is_advertising=true&ad_domain=VIPDESKTOP_UP&ad_position=11&ad_click_id=NTU1MTE2ODctNzNjMS00MzY0LThkODMtODIwZGE1NGUxNzQy