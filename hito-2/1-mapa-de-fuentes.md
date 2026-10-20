# Mapa de fuentes

**Documento 1 de 4 del Hito 2**

---

**Equipo:** Jorge Federico Flores, Nicolás Velázquez, Nilayvi Barrientos, Rubén Ortigoza

**El dato del que más depende el proyecto:** pares foto + ficha validados por humanos en catálogos de marcas argentinas de indumentaria chicas o medianas ([canvas](../canvas.md), sección 5). Sin ellos no podemos medir si acertamos con fotos como las del usuario ni entrenar el control de coherencia foto vs. ficha.

---

## 1. Fuentes evaluadas

| # | Fuente | Origen | ¿Está disponible hoy? (quién la abrió) | ¿Qué tan complejo es obtenerla? (tiempo, esfuerzo, dinero) | ¿Es sensible, tiene dueño? (términos de uso, licencia) | Volumen estimado |
|---|---|---|---|---|---|---|
| 1 | Pares foto + ficha cargados por personas en marcas argentinas (marcas piloto) | De terceros (*second-party*: el catálogo de cada marca, compartido por acuerdo). Lo genera el usuario del producto al cargar | **No.** Nadie del equipo la abrió. No contactamos marcas todavía: las entrevistas del canvas (sección 1) siguen pendientes | Alta. Hay que conseguir marcas que acepten, firmar un acuerdo de uso de datos y exportar el catálogo (fotos + campos) de su plataforma. *(H)* Semanas, no días. Dinero: ninguno directo | Sí. Cada marca es dueña de sus fotos y fichas. Si hay fotos con modelos, los rostros son datos personales (Ley 25.326). Mandar las fotos a un servicio externo requiere que la marca lo sepa y lo acepte (canvas, sección 5) | No sabemos. *(H)* Entre decenas y unos pocos cientos de prendas por marca y por colección (canvas, sección 1) |
| 2 | CSV etiquetados de `img-puller` (`tops_tags.csv`, `shoes_tags.csv`, `pants_tags.csv`) del prototipo [MatLock/UdeSA-computer-vision](https://github.com/MatLock/UdeSA-computer-vision) | De terceros. Según el canvas, "clientes productivos con autorización"; no sabemos de qué empresa ni de qué cliente. Las imágenes se sirven desde `ruecdn.com` *(H: CDN de Rue La La, retailer off-price de EE. UU.; se verifica en el EDA)* | **Sí.** Está en la carpeta `img-puller/data/` del prototipo. El equipo la usó para entrenar los modelos de atributos (canvas, sección 5: "¿Lo vimos? Sí") | Baja. Los CSV pesan pocos MB y se bajan del repo fijando un commit. Las imágenes se bajan por URL desde un CDN ajeno: hay que hacerlo con pausa y puede haber URLs muertas | **No sabemos.** El permiso explícito para usarlos en la materia y publicar un extracto está pendiente de confirmación de Jorge. Si las imágenes son de un retailer, sus fotos tienen dueño aunque estén visibles en la web | Unas 50.000 imágenes, según el canvas. El número real lo cuenta el EDA |
| 3 | Fashion Product Images (Myntra), en Kaggle (`paramaggarwal/fashion-product-images-dataset`) y en versión chica en Hugging Face (`ashraq/fashion-product-images-small`) | De terceros (*third-party*, dataset público) | Sí, es pública. **Nadie del equipo la abrió todavía:** solo leímos la ficha (canvas, sección 5) | Baja. Se baja con una cuenta de Kaggle o desde Hugging Face, sin costo. La versión completa es pesada; la chica alcanza para contar columnas y comparar | Licencia a verificar en Kaggle. Las fotos son de Myntra, con modelos | Unos 44.000 productos, con título (`productDisplayName`), tipo (`articleType`), color (`baseColour`), temporada y uso (canvas, sección 5) |
| 4 | Títulos y descripciones **sintéticos** para las imágenes de la fuente 2, generados con `img-puller/describer.py` | Sintético (lo generaríamos nosotros con Claude, a partir de la imagen y los tags) | **No existe todavía.** El código está en el prototipo, pero nunca se corrió: los CSV no tienen columnas `title` ni `description` | Media. Una llamada a un modelo multimodal por imagen (hasta unas 50.000), con costo de API. Además, una persona tiene que revisar una muestra *(H: unas 300)* para medir la tasa de error | Hereda los permisos de las imágenes de la fuente 2. Hay que revisar los términos de uso del generador, porque algunos proveedores restringen usar sus salidas para entrenar otros modelos | Hasta uno por imagen de la fuente 2 |

## 2. Riesgos anticipados por propiedad

| # | Completitud (qué puede faltar y por qué) | Corrección (errores, formato, duplicados) | Vigencia (período que cubre) | Representatividad (a quién deja afuera) | Confiabilidad (quién generó, verificó y homologó el dato; quién etiquetó) |
|---|---|---|---|---|---|
| 1 | Material y composición solo si la marca los carga (muchas publican con la ficha mínima: foto y precio, canvas §1). Descripciones vacías o copiadas de otra prenda | Vocabulario distinto según quién cargó ("buzo", "hoodie", "canguro"). Fichas duplicadas de una prenda parecida con datos sin actualizar. Colores mal puestos, que es justo el error que motiva el producto | Buena si se exporta el catálogo vigente. **No sabemos** si las plataformas guardan el historial de temporadas anteriores | Solo las marcas que acepten participar: probablemente las más ordenadas y con mejores fotos. Deja afuera a las que publican con fotos caseras | **No sabemos.** La ficha la escribe la persona que carga, sin verificación ni homologación entre marcas. No hay una segunda persona que controle |
| 2 | Según lo que conocemos de los encabezados, no hay columnas de color, tipo de prenda, material, género, título, descripción ni fecha. Las URLs de un CDN ajeno pueden haber dejado de responder | `shoes_tags.csv` repite la columna `relative_path` en el encabezado. Puede haber etiquetas con formato mezclado y duplicados de producto (mismo modelo en varios colores). **No sabemos** la tasa de etiquetas erróneas | **No sabemos.** No hay columna de fecha. *(H)* Productos de un retailer de EE. UU. de los últimos años | Si se confirma el origen en EE. UU., deja afuera a las marcas argentinas chicas y sus fotos. Solo hay tres categorías (tops, calzado, pantalones): faltan vestidos, abrigos y accesorios. Las temporadas son las del hemisferio norte | **No sabemos** quién o qué generó los tags (personas, un modelo o un modelo revisado), con qué taxonomía ni con qué control de calidad. Pendiente de respuesta de Jorge |
| 3 | Título corto y sin descripción larga. Sin material | **No sabemos.** Puede haber duplicados y clases mal asignadas, como en cualquier catálogo cargado a mano | **No sabemos** el período exacto. *(H)* Catálogo de Myntra de mediados de la década de 2010 | Retail de India, fotos con modelo, títulos en inglés con la marca adelante. Deja afuera al vocabulario y las fotos de marcas argentinas | Las fichas las cargó el retailer. **No sabemos** si hubo una verificación aparte |
| 4 | Lo que el generador no puede ver en la foto: material, composición, talle. Si lo inventa, enseña a inventarlo (canvas §5) | Hereda los errores de los tags de la fuente 2 y agrega los del modelo, que inventa atributos finos (canvas, fuente 12). Textos parecidos entre sí | La misma que la fuente 2: **No sabemos** | El español rioplatense sale de la generación, no de una persona. Hereda la representatividad de la fuente 2 | La genera un modelo. La verificaría una persona del equipo sobre una muestra. Como el texto se arma **mirando los tags**, depende de las etiquetas |

## 3. Plan de obtención

| # | Quién del equipo la consigue | Para cuándo |
|---|---|---|
| 1 | Nicolás y Nilayvi: contactar 3 a 5 marcas argentinas chicas, empezando por las de las entrevistas de la sección 1 del canvas | Respuesta de las marcas: 2026-10-31. Los datos, para el Hito 3 |
| 2 | Jorge: confirmar el origen y el permiso de uso de los CSV. Nicolás: armar la muestra con `scripts/armar_muestra.py` | 2026-10-24 |
| 3 | Nilayvi: bajar `styles.csv`, verificar la licencia y contar las filas con título | 2026-10-27 |
| 4 | Nadie en este hito. Queda para el Hito 3, si el veredicto lo sostiene | — |

## 4. Resultado de la obtención

| # | Qué se obtuvo (o por qué no) | Es la muestra que se entrega (sí / no) | Qué cambió respecto de lo que esperaban |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
