# AI Opportunity Canvas

> **Equipo:** Deep Tagger
> **Integrantes:** Jorge Federico Flores, Hernán Marano, Nicolás Velázquez
> **Caso:** Carga y control de fichas de producto para e-commerce de moda (lado empresa, no consumidor final)
> **Proyecto que extendemos:** [MatLock/UdeSA-computer-vision](https://github.com/MatLock/UdeSA-computer-vision). Cuando este documento dice "el repo" o "el prototipo", se refiere a ese proyecto.
> **Versión:** 1 · **Fecha:** 2026-09-28

Convención de este documento: lo marcado como *(H)* es hipótesis nuestra, todavía sin verificar. Lo que no tiene marca tiene una fuente al final. Si algo dice "no sabemos", es que no sabemos.

---

## 1. Problema y contexto

### A quién le pasa

Quien carga el catálogo en una marca de indumentaria argentina chica o mediana: la dueña, o la persona de e-commerce (equipos de 1 a 5). Le pasa cada vez que entra una colección o una reposición y hay que publicar un lote de prendas en la tienda propia y/o en un marketplace. Cuántas prendas por lote es un dato que no tenemos *(H: entre decenas y unos pocos cientos)*.

Tamaño del grupo, como proxy: Tiendanube dice tener más de 60.000 tiendas en Argentina (todos los rubros, no solo moda) y la CACE midió 25,1 millones de compradores online en 2025. Cuántas de esas tiendas son de indumentaria, no sabemos.

### Qué le pasa

El progreso que busca: tener las prendas online rápido, bien descriptas y encontrables, sin prometer algo que la prenda no es.

- Funcional: publicar cada prenda con la ficha completa y consistente (categoría, color, material, temporada, título, descripción) sin pasar horas.
- Social: que la marca se vea prolija frente a sus clientas y frente a la competencia, y que nadie escriba "no era como en la foto".
- Emocional: sacarse de encima una tarea repetitiva, y el miedo a haber puesto mal un color o una tela y comerse el reclamo después.

Circunstancia: llega la mercadería, hay fotos, hay una fecha de lanzamiento, y quien carga está solo/a o con poca gente, en medio de otras tareas (atender consultas, armar pedidos, subir a redes).

Cómo lo diría alguien en esa situación *(texto armado por nosotros como ejemplo, no es un testimonio real; hay que reemplazarlo por uno de verdad)*:

> "Me llegan 80 prendas nuevas un jueves y las quiero online el lunes. Cada una tiene que tener su color, su tela, su categoría, un título y una descripción que no sea copiar la de la remera anterior. Termino duplicando la ficha vieja y cambiando lo que me acuerdo. Después me llega un reclamo de que el verde era más oscuro."

Obstáculos: volumen repetitivo; cada plataforma pide campos y categorías distintas; hay atributos que se ven en la foto y otros que solo se saben con la etiqueta en la mano; quien carga cambia de una temporada a otra y cada uno describe distinto ("buzo", "hoodie", "canguro").

Cómo se las arregla hoy: planilla y copiar/pegar, plantillas de descripción, copiar lo que manda el proveedor, delegar en un pasante o un freelance, o publicar con la ficha mínima (foto y precio). Cuánta gente hace cada cosa no lo sabemos.

Calidad para esta persona: que la ficha salga casi hecha y que lo dudoso esté señalado. Aceptaría revisar algunos campos, pero no revisarlos todos.

### Cuánto le cuesta

No tenemos una medida propia. Lo que hay son proxies, todos de fuentes secundarias y ninguno de Argentina:

- Tiempo por prenda cargada: **no lo sabemos**. Hay que cronometrarlo (ver sección 6).
- Devoluciones: en moda online, entre el 10% y el 20% de las devoluciones se atribuyen a que el artículo no coincide con la foto o con la descripción (10% según un desglose atribuido a DHL; 16% y 20% según otras dos fuentes).
- Fuera de nuestro alcance, pero importante para dimensionar: talle y calce pesan más (26% a 40% de las devoluciones de moda según las mismas fuentes). Ver sección 3.

### Evidencia

#### De confirmación

- Las devoluciones por diferencia entre lo publicado y lo recibido existen y están medidas por terceros (fuentes 1 y 2), aunque no en Argentina.
- El e-commerce argentino es grande y sigue creciendo: facturó $34 billones en 2025 (+55% nominal) y vendió 645 millones de unidades (fuente 3).
- *(H)* Pendiente: entrevistar a 8 o 10 dueños o encargados de e-commerce de marcas argentinas y preguntar cómo cargan y cuánto tardan. Todavía no lo hicimos.

#### De refutación

- Según la CACE, en 2025 indumentaria salió de los primeros lugares en facturación y unidades (fuente 4). El rubro pesa menos de lo que suponíamos.
- Los porcentajes de devolución son de España/EE.UU./blogs de logística. Puede que en Argentina el motivo principal sea otro.
- Lo que refutaría el problema: que las marcas entrevistadas carguen el catálogo una vez por temporada, les lleve poco, y no lo vivan como un dolor. Hasta no entrevistar, no lo descartamos.

---

## 2. Stakeholders

### Roles

| Papel | Quién es | Qué necesita ver para decir que sí |
|---|---|---|
| Usuario | Quien carga el catálogo: encargada/o de e-commerce, community manager, pasante *(H)* | Que la ficha salga casi hecha y que corregir sea más rápido que escribir desde cero |
| Influenciador | Fotógrafo/a o diseñador/a de la marca; el referente técnico si la tienda tiene agencia *(H)* | Que no le cambien la forma de nombrar las prendas ni la línea de fotos |
| Recomendador | Dueño/a cuando no es quien paga; la agencia que administra la tienda *(H)* | Ver otra marca parecida que lo use y le vaya bien |
| Comprador | Dueño/a de la marca o gerente de e-commerce | Un costo mensual menor a lo que hoy gasta en tiempo o en quien carga |
| Decisor | Dueño/a. En una pyme suele ser el mismo que el comprador *(H)* | Que no publique cosas equivocadas que generen reclamos |
| Saboteador | Agencias o freelancers que hoy cobran por cargar catálogo; los marketplaces si lanzan algo propio *(H)* | Nada que podamos ofrecerles; es un riesgo a monitorear |

Reconocimiento del problema (los tres escalones de la consigna): *(H)* creemos que la mayoría está en el segundo (lo sabe y le duele, pero no hizo nada), y que una minoría ya tiene un apaño (plantillas, delegar). Sin entrevistas no podemos afirmarlo.

### Evidencia

#### De confirmación

- Ninguna todavía, más allá de razonamiento propio. Lo que sí sabemos es que hay tiendas chicas en plataformas como Tiendanube, lo que hace plausible que el usuario y el comprador sean la misma persona.

#### De refutación

- Si el usuario (quien carga) y el comprador (quien paga) fueran personas distintas y el que paga no viera el costo del tiempo de carga, no habría presupuesto. Hay que averiguar si hoy la marca paga algo por esta tarea (sueldo, pasante, agencia). Si no paga nada y lo hace la dueña "gratis", el comprador no existe todavía.

---

## 3. Hipótesis de solución

### Descripción del producto

Una herramienta para equipos de e-commerce de moda. Se suben las fotos de una prenda y devuelve la ficha lista para revisar: tipo de prenda, color, material probable, temporada, ocasión, título y descripción. Cada campo indica qué tan seguro está, y los dudosos quedan marcados para revisión. También se le puede pasar una publicación ya cargada y avisa cuando algún dato de la ficha no coincide con la foto. La salida se adapta al formato que pide cada plataforma.

Lo que ya existe en el repo ([UdeSA-computer-vision](https://github.com/MatLock/UdeSA-computer-vision)): subir una URL de imagen y recibir tipo de prenda, colores dominantes, algunos atributos (material, ocasión, temporada) para tops, calzado y pantalones, título y descripción.

Lo que proponemos sumar:

1. **Control de coherencia foto vs. ficha** (nuevo, usa ML). Es lo que más se acerca al problema de las devoluciones por "no coincide".
2. **Confianza por campo y cola de revisión** (nuevo, usa ML). La persona revisa solo lo dudoso.
3. **Registro de correcciones** de quien revisa. Es el dato que hoy no existe (ver sección 5).
4. **Más atributos y más tipos de prenda**: estampa, tipo de cuello, largo de manga, largo de la prenda, vestidos, abrigos, accesorios. Hoy hay 10 clases de prenda y atributos solo para 3 categorías.
5. **Vocabulario local**: remera, buzo, campera, jogger, pollera.
6. **Exportación a la planilla de carga masiva** de cada plataforma (esto es una regla, no ML).

Qué se resuelve sin ML: mapear a categorías de cada plataforma, plantillas de título, validación de campos obligatorios, exportar. Decirlo ahorra tiempo.

Qué porción del problema cubre: el desajuste entre lo publicado y la foto/descripción. No cubre talle ni calce, que según las fuentes pesan más en las devoluciones de moda. Hay que ajustar la sección 1 si decidimos que el producto no apunta a eso, o ampliar el alcance más adelante.

### Acción

Quien carga acepta la ficha sugerida, revisa solo los campos marcados como dudosos y publica. En publicaciones existentes, corrige las que la herramienta marcó como incoherentes. Cambia que deja de completar todo desde cero y pasa a revisar excepciones. Quien decide es la persona de e-commerce, al subir cada prenda o lote.

### Predicción

Para cada prenda y cada atributo: el valor más probable y qué tan seguro está. Para el control de coherencia: la probabilidad de que un dato declarado en la ficha no corresponda a lo que se ve en la foto.

Una advertencia: el material (algodón, lino, poliéster) muchas veces no se distingue en una foto. Puede que para ese atributo la predicción no sea posible y haya que pedirlo al usuario o leerlo de la etiqueta.

### Juicio

Cuánto cuesta publicar un dato equivocado (un reclamo, una devolución, una prenda que no aparece en los filtros) contra cuánto cuesta revisar un campo de más (unos segundos de quien carga). De eso sale el umbral de confianza a partir del cual la herramienta marca un campo para revisión.

*(H)* Punto de partida: umbral más exigente para tipo de prenda y color (generan más reclamos) que para temporada y ocasión (más subjetivos). Nadie de una marca real lo validó ni lo firmó. Lo tiene que fijar la dueña o el gerente de e-commerce, no nosotros.

### Evidencia

#### De confirmación

- La decisión existe hoy: alguien mira la foto (y la etiqueta) y completa la ficha, prenda por prenda. Tiempo y frecuencia: no medido.
- Existen servicios comerciales de etiquetado automático de moda (se mencionan en sección 4), lo que sugiere que la predicción es posible. Verificar cuánto aciertan y con qué tipo de fotos.
- Nuestro prototipo ya devuelve tipo, color, atributos, título y descripción para una URL (hay un video demo en el repo). No tenemos medida de acierto sobre fotos reales de catálogos argentinos.

#### De refutación

- Si quien carga revisa todos los campos igual, porque no confía en la sugerencia, la herramienta no ahorra tiempo y la acción no cambió. Se prueba dándole el prototipo a 3 o 4 personas y contando cuántos campos cambian.
- Un modelo multimodal generalista (por ejemplo Claude, GPT o Gemini con la foto y un prompt) podría hacer lo mismo o mejor sin entrenar nada. Si al probarlo con 100 fotos supera a nuestro pipeline, hay que replantear qué aporta el modelo propio. Todavía no hicimos esa comparación.
- Que nadie quiera fijar el umbral (cuánto vale un error) sería un problema del proyecto, no técnico.

---

## 4. Alternativas y statu quo

### Qué hace hoy el usuario

Carga a mano en el formulario de la plataforma o en una planilla de carga masiva. Reutiliza la ficha de una prenda parecida. Copia lo que manda el proveedor. Delega en un pasante o freelance. *(H)* Es probable que ya use un asistente de chat para redactar descripciones, lo que hay que confirmar preguntando.

Costo de hacerlo así: tiempo por prenda (no medido), fichas inconsistentes entre temporadas, errores que aparecen como reclamos.

Qué tiene de bueno: no cuesta nada extra, tiene la prenda en la mano (puede leer la etiqueta y tocar la tela), y controla lo que dice cada ficha.

### Qué otras soluciones existen o podrían aparecer

- Servicios de etiquetado automático de moda vía API (por ejemplo Ximilar, Vue.ai u otros). No verificamos precios, cobertura de atributos ni si funcionan para el mercado argentino.
- Herramientas de las propias plataformas (Tiendanube, Mercado Libre) que sugieran categorías o atributos. Hay que revisar qué ofrecen hoy; pueden lanzar algo mientras construimos.
- Modelos multimodales generalistas usados a mano por el propio usuario.

### Por qué lo nuestro sería suficientemente mejor como para que alguien se mueva

Hipótesis, en orden de qué tan defendibles nos parecen:

1. El control de coherencia foto vs. ficha con confianza por campo. No lo vimos en las alternativas, pero no las revisamos a fondo.
2. Vocabulario y categorías locales, y salida directa a la planilla de cada plataforma.
3. Aprender de las correcciones de cada marca (su forma de nombrar, su paleta).
4. Precio pensado para pymes argentinas. No sabemos qué pagarían.

Nada de esto está demostrado. El primer paso para sostenerlo es la comparación contra un modelo generalista de la sección 3.

### Evidencia

#### De confirmación

- Ninguna propia todavía. Falta observar a una persona cargando 10 prendas y ver qué hace, con qué herramientas y cuánto tarda.

#### De refutación

- Puede que el statu quo (plantillas + un asistente de chat) ya sea suficiente para la mayoría y la mejora sea chica. Es el caso a descartar primero.
- Puede que las plataformas ya sugieran atributos a partir de la foto, con lo cual el hueco no existe.

---

## 5. Hipótesis de datos

Enfoque: aprendizaje supervisado. La respuesta correcta es la ficha que un humano validó para esa foto.

### Dataset

| Dato | Origen | ¿Público? | ¿Lo vimos? | ¿Sensibles? | Sesgo conocido | Comentarios |
|---|---|---|---|---|---|---|
| Fashion-MNIST (70k imágenes, 10 clases) | Zalando Research | Sí | Sí, entrenamos con él | No | Imágenes de 28×28 en gris, sobre fondo limpio, pocas clases; no se parece a una foto de catálogo real | Entrena el clasificador de tipo de prenda |
| CSV con imágenes etiquetadas (tops, pantalones y otros) que baja `img-puller`: unas 50.000 imágenes con algunos tags y tipo de producto, **sin título ni descripción** | no: quién etiquetó y de dónde vienen las imágenes | clientes productivos con autorizacion | Sí | No | No | Entrena los atributos (material, ocasión, temporada). Hay inconsistencia a revisar: `img-puller` nombra "dresses" y la API tiene modelos para "tops, shoes, pants". *(H)* Ver si sale de Fashion Product Images (fila de abajo): el tamaño y los atributos se parecen, y ese dataset sí trae título |
| Fashion Product Images: unos 44.000 productos con `gender`, `masterCategory`, `subCategory`, `articleType`, `baseColour`, `season`, `usage` y `productDisplayName` (título) | Kaggle (paramaggarwal), catálogo de Myntra. Hay una versión chica en Hugging Face (`ashraq/fashion-product-images-small`) | Sí. Licencia: verificar en Kaggle | No | Fotos con modelo | Retail de India. Títulos cortos con marca ("Turtle Check Men Navy Blue Shirt"), sin descripción larga | Trae título real, temporada y ocasión (`usage`), lo mismo que predice el prototipo |
| H&M: unos 105.000 artículos con `prod_name`, `detail_desc` (descripción), tipo, color e imagen | Competencia de Kaggle "H&M Personalized Fashion Recommendations". En Hugging Face: `Qdrant/hm_ecommerce_products` (completo) y `wbensvage/clothes_desc` (1.000 pares imagen + texto) | Sí, bajo las reglas de la competencia | No | Fotos con modelo. Las transacciones y clientes no los necesitamos | Una sola marca, fast fashion europea, en inglés y con el estilo de redacción de H&M | Es lo más parecido a "foto + ficha escrita por la marca". El espejo de Qdrant dice CC BY 4.0, pero no puede cambiar la licencia de datos que no son suyos: leer las reglas de la competencia |
| Amazon Reviews 2023, categoría Clothing, Shoes & Jewelry: 7,2 millones de ítems con `title`, `description`, `features`, `details` (incluye material) e `images` | McAuley Lab (UCSD), Hugging Face `McAuley-Lab/Amazon-Reviews-2023` | Sí, pensado para investigación. La página no publica licencia | No | Los metadatos no; las reseñas tienen ids de usuario y no las usaríamos | EE. UU., en inglés. Textos escritos por vendedores, de calidad muy despareja y con mucho marketing | Volumen enorme. Hay que filtrar un subconjunto limpio. Es de las pocas fuentes que trae material declarado |
| Fashion-Gen: unas 293.000 imágenes de 1360×1360 con descripción escrita por estilistas; 48 categorías y 121 subcategorías | Element AI y SSENSE (paper de 2018) | Bajo pedido. Licencia no verificada | No | Algunas con modelo | Lujo, fondo uniforme, en inglés | Las descripciones son las más parecidas a una ficha de catálogo. Hay que ver si todavía se puede pedir |
| DeepFashion-MultiModal: 44.096 imágenes con atributos manuales de forma, tela (7 clases) y color/estampa (7 clases), más una descripción por imagen | CUHK MMLab | Sí, **solo investigación no comercial** | No | Sí: fotos de personas de cuerpo entero | Todas con modelo, sin fondo de catálogo. Las descripciones salen de plantillas | Sirve para tela y estampa con anotación manual, y para medir cómo anda el prototipo con fotos con modelo. No se puede usar en un producto comercial |
| Fashionpedia: 48.825 imágenes, 27 categorías, 294 atributos finos (cuello, manga, largo, estampa) con máscaras | Google, Cornell y CVDF | Anotaciones CC BY 4.0. Las imágenes tienen la licencia de cada origen (Flickr, Unsplash, Pexels, etc.) | No | Sí: personas en la calle y en eventos | Fotos de la vida real, no de catálogo | Fuente de los atributos que queremos sumar (sección 3, punto 4). No trae títulos ni descripciones |
| Fashion200k: unas 200.000 imágenes con descripción corta y tres niveles de categoría | Han et al. (2017). Espejo en Hugging Face `Marqo/fashion200k` | Sí (el espejo dice Apache 2.0; las imágenes vienen de tiendas online) | No | Algunas con modelo | Retail de EE. UU. | Las descripciones son listas de atributos ("blue denim skinny jeans"): sirven más para títulos que para descripciones |
| Títulos de publicaciones de Mercado Libre en español y portugués, con categoría | MeLi Data Challenge 2019 (competencia pública de Mercado Libre; también en Kaggle) | Sí. Términos a revisar | No | No | Todos los rubros (hay que filtrar indumentaria) y categorías de Mercado Libre. No trae imágenes | La única fuente orgánica en español que encontramos. Muestra cómo se titula en la región ("remera", "buzo", "campera") |
| Títulos y descripciones **sintéticos** para las ~50.000 imágenes del repo | Generados por nosotros con un modelo multimodal, a partir de la imagen y los tags que ya tiene | Propio | No existe todavía | No, mientras no usemos fotos de clientes | Hereda los errores y el estilo del modelo que los genera. Tiende a descripciones parecidas entre sí | Ver "Datos orgánicos y sintéticos" abajo |
| Fichas con errores **inyectados** (color, tipo o material cambiados a propósito) | Generadas por nosotros a partir de fichas reales | Propio | No existe todavía | No | El error es artificial: puede no parecerse a los errores que comete una persona | Entrena y evalúa el control de coherencia foto vs. ficha |
| Imágenes de productos de marketplace (el ejemplo del README usa una URL de mlstatic.com) | Mercado Libre, si ese es el origen | Visible en la web, pero eso no es lo mismo que libre de usar | Parcialmente | Fotos con modelos = imagen de personas | Marcas grandes y fotos profesionales | Revisar términos de uso antes de seguir usándolas para entrenar |
| Pares foto + ficha cargados por humanos en marcas argentinas | Clientes o marcas piloto | No | **No** | Rostros de modelos | Depende de cada marca | Es el dato del que más depende el proyecto |
| Correcciones de quien revisa (campo, valor sugerido, valor final) | Uso de la herramienta | No | **No existe todavía** | No | — | Hay que empezar a registrarlo desde el primer uso |
| Devoluciones con motivo | Marcas piloto | No | No | Datos de compradores | — | Para validar impacto a largo plazo |
| Campos y categorías que exige cada plataforma | Documentación de las plataformas | *Completar* | No | No | — | Es lo que define la salida de la herramienta |

Dato del que más depende: los pares foto + ficha validados por humanos en catálogos reales. Sin ellos no podemos medir si acertamos ni entrenar el control de coherencia.

Extrapolable entre clientes: parcialmente. Los conceptos (color, tipo) sí, pero cada marca tiene su vocabulario, su paleta y su forma de fotografiar.

Datos personales: los rostros de modelos son datos personales (Ley 25.326). Además, mandar las imágenes de un cliente a un servicio externo para generar la descripción requiere que el cliente lo sepa y lo acepte. Hay que definirlo antes de un piloto.

### Datos orgánicos y sintéticos

El hueco concreto: las ~50.000 imágenes del repo tienen tipo de producto y algunos tags, pero no tienen título ni descripción. Sin texto escrito para esas fotos no podemos entrenar ni medir la parte que genera la ficha. Proponemos usar los dos tipos de dato, cada uno para una cosa distinta:

- **Orgánicos** (escritos por personas: H&M, Fashion Product Images, Amazon, Fashion-Gen, Mercado Libre y, más adelante, las marcas piloto). Sirven para entrenar donde alcanzan y, sobre todo, para **evaluar**. El set de evaluación es 100% orgánico. Nunca medimos contra texto sintético.
- **Sintéticos** (generados por nosotros). Sirven para dos cosas: (1) completar título y descripción de las ~50.000 imágenes, en español rioplatense, que es lo que no existe en ningún dataset público con imagen; (2) armar fichas con errores inyectados para el control de coherencia.

Cómo armaríamos los títulos y descripciones sintéticos *(H, sin probar)*:

1. Un modelo multimodal recibe la imagen y los tags que ya tiene, y escribe título y descripción. Los tags van como restricción: el texto no puede contradecir el tipo ni el color conocidos.
2. Un filtro automático descarta los textos que contradicen los tags o que mencionan material cuando el tag no lo trae. El material casi nunca se ve en la foto (sección 3), y un texto sintético que lo inventa enseña a inventarlo.
3. Una persona del equipo revisa una muestra (*H: unas 300*) y anota cuántos tienen errores. Esa tasa se reporta junto con cualquier resultado que use el dato sintético.
4. Entrenamos con sintético y orgánico mezclados, y medimos solo sobre orgánico.

Lo que hay que tener presente con lo sintético:

- **Circularidad con la sección 3.** Si el texto de entrenamiento lo escribe un modelo generalista, el nuestro como mucho lo imita. La comparación "nuestro pipeline vs. un modelo generalista" queda sesgada a favor del generalista en calidad de texto. Lo que el modelo propio podría aportar es costo, velocidad, vocabulario local y el control de coherencia, y hay que medirlo en esos términos.
- Los modelos multimodales inventan atributos finos (fuente 12). El dato sintético va a tener errores, y por eso se mide su tasa.
- Homogeneización: si todas las descripciones salen del mismo generador, todas suenan igual (sección 7, riesgo social).
- Términos de uso del generador: algunos proveedores restringen usar sus salidas para entrenar otros modelos. Revisarlo antes de generar.
- Idioma: casi todo lo orgánico con imagen está en inglés. El español rioplatense sale de traducción o generación, o sea, también es sintético. Los títulos de Mercado Libre son la única referencia orgánica en español, y no traen imagen.

Licencias: varios de estos datasets son solo para investigación no comercial (DeepFashion-MultiModal seguro; H&M, Amazon y Fashion-Gen sin confirmar). Para la PoC de la materia alcanza. Para un producto no alcanza, y el dato del que más depende el proyecto sigue siendo el mismo: fichas reales de marcas argentinas.

### Evidencia

#### De confirmación

- Abrimos y usamos Fashion-MNIST y los CSV etiquetados del repo. Sabemos que tienen las columnas necesarias para los tres tipos con modelo de atributos.
- Existen datasets públicos de moda con pares imagen + texto escrito por personas: H&M, Fashion Product Images, Amazon Reviews 2023, Fashion-Gen, DeepFashion-MultiModal y Fashion200k (fuentes 6 a 11). Leímos las fichas de cada uno en Hugging Face, GitHub o el paper, pero **no abrimos ninguno todavía**. Por eso en la tabla dicen "No".
- Generar texto sintético a partir de imágenes de moda es una práctica publicada (fuente 12), así que lo que proponemos es posible.

#### De refutación

- Fashion-MNIST no representa fotos reales de catálogo. Es probable que el clasificador de tipo rinda peor con fotos con modelo, fondos complejos o prendas fuera de esas 10 clases. Todavía no lo medimos con fotos reales.
- El cálculo de color descarta píxeles blancos y agrupa en 2 colores. Con una modelo puesta la prenda, la piel, el pelo y el fondo se van a colar. Falta probarlo.
- No conocemos el origen de los CSV etiquetados, y eso puede invalidar el uso.
- No encontramos ningún dataset público con imagen + ficha en español, ni de marcas argentinas. Todo lo orgánico con imagen es de EE. UU., Europa o India.
- La misma literatura que genera descripciones sintéticas dice que los modelos multimodales sin ajuste inventan o confunden atributos finos (fuente 12). Si la tasa de error del sintético resulta alta, no sirve para entrenar.
- Las licencias de H&M, Amazon y Fashion-Gen no están confirmadas. Si alguna prohíbe el uso fuera de su competencia o fuera de investigación, sale de la tabla.

Próximo paso concreto: bajar `articles.csv` de H&M y `styles.csv` de Fashion Product Images, contar cuántas filas tienen título y descripción no vacíos, y ver si las ~50.000 imágenes del repo coinciden con las de Fashion Product Images (si coinciden, ya tienen título orgánico).

---

## 6. Métrica de éxito

### Métrica de negocio

Minutos de trabajo por prenda publicada, desde que la foto está lista hasta que la ficha está publicada, con la herramienta contra sin ella. Como complemento: porcentaje de campos que la persona modifica antes de publicar.

A largo plazo (no medible dentro del trimestre): porcentaje de devoluciones por "no coincide con la descripción/foto" en las marcas piloto.

### Umbral — por debajo de esto, no vale la pena

*(H) Provisorio, hasta tener la línea de base:*

- Menos de 30% de reducción del tiempo por prenda: no vale la pena.
- Si la persona modifica más del 20% de los campos de tipo y color: sigue revisando todo y no ahorra nada.

Estos números están puestos antes de construir, pero salen de nuestra intuición. Se ajustan con la medición de abajo.

### Cómo se mediría dentro del trimestre, aunque sea de forma aproximada

Conseguir 3 o 4 personas que cargan catálogo de moda (marcas conocidas, aunque sea informal). Cronometrar la carga de 20 a 30 prendas a mano y otras 20 a 30 con el prototipo, y anotar cuántos campos cambian. La muestra es chica y no permite conclusiones estadísticas, pero da una línea de base y un orden de magnitud.

### Métrica técnica que usaríamos como proxy

F1 por atributo (tipo, color, ocasión, temporada) sobre un set de fotos reales etiquetadas por nosotros. Para el control de coherencia: precisión y recall de las discrepancias detectadas, sobre un set con errores agregados a propósito (esto es artificial y hay que decirlo cuando se reporte). Sirve para saber si el modelo mejora de una semana a otra; no reemplaza a la métrica de negocio.

### Qué se registra de cada uso

Por cada prenda: id de la imagen, valor sugerido y confianza de cada campo, valor final publicado, si fue modificado, tiempo hasta publicar y a qué plataforma se exportó.

### Evidencia

#### De confirmación

- Tiempo por prenda es medible sin construir nada más que el cronometraje. Con el prototipo actual ya se puede correr la parte "con herramienta".

#### De refutación

- No hay línea de base: nadie sabe cuánto tarda hoy, y por eso el umbral es todavía un número inventado. Si las marcas no lo miden, la línea de base la armamos nosotros con una muestra chica.

---

## 7. Riesgos éticos y de sesgo (preliminar)

Sobre quién decide el sistema aunque no lo use: las compradoras finales. Lo que la herramienta escribe sobre una prenda decide cómo la ven y si la encuentran.

**Asignación.** Una prenda mal categorizada o con el color equivocado no aparece en los filtros y no se vende. Para una marca chica es visibilidad perdida. Si la herramienta hace una tarea que antes se revisaba a mano, el error pasa más desapercibido.

**Calidad de servicio.** Probablemente ande peor con: prendas fuera de las clases de entrenamiento (ropa tradicional, talles grandes, ropa infantil, ropa de trabajo), fotos con modelo o sobre fondo no blanco, estampas y colores fuera del diccionario de colores, y las marcas chicas con fotos caseras. *(H)* A medir: acierto por tipo de prenda, tipo de foto y marca.

**Representación.** Las categorías con las que el sistema nombra las prendas (10 clases, "casual/formal", varón/mujer) pueden no calzar con la ropa sin género, o reforzar estereotipos en las descripciones generadas ("ideal para una noche elegante").

**Interpersonal.** Las fotos con modelos son imagen de personas; enviarlas a un servicio externo sin acuerdo es un problema. También el uso de imágenes de terceros para entrenar (sección 5).

**Social.** A escala, los títulos y descripciones se homogenizan y el catálogo de todas las marcas suena igual. Se pierde el trabajo de quien redacta y se puede degradar el posicionamiento en buscadores por contenido repetido. Efecto sobre el empleo de quienes hoy cargan: no lo sabemos.

**Proxy.** El origen de las imágenes (marcas grandes con fotos profesionales) puede estar haciendo de proxy de "calidad de foto" o "nivel socioeconómico de la marca".

**Para qué no debería usarse.** Para publicar sin revisión humana, sobre todo en material, talle o composición. La ley de defensa del consumidor (24.240) exige información veraz sobre el producto y la responsabilidad es del vendedor, no de la herramienta.

**Si se equivoca, ¿cómo se entera la persona?** Hoy no hay un mecanismo. Por eso la sección 6 pide registrar correcciones y el diseño incluye confianza por campo.

Regulación: no toca las categorías críticas de la lista (empleo, crédito, biometría, etc.), salvo por las fotos con rostros. Leer Ley 25.326 y 24.240 antes de un piloto.

### Evidencia

#### De confirmación

- Fashion-MNIST se creó como reemplazo simple de MNIST, no como representación de catálogos reales.
- Las devoluciones por diferencia entre lo publicado y lo recibido están documentadas (fuentes 1 y 2), así que el costo de un dato mal puesto es real.

#### De refutación

- Falta buscar casos publicados de sistemas de etiquetado de moda que hayan fallado por sesgo. Hasta ahora no encontramos uno concreto, así que no podemos afirmar que estos riesgos hayan pasado en la práctica.
- Si la herramienta siempre queda con revisión humana antes de publicar, varios de estos riesgos bajan. Habría que poder decir por qué en cada caso.

---

## Fuentes consultadas (2026-09-28)

1. asest.es, "comercio electrónico con una menor tasa de devoluciones": motivos de devolución (tabla atribuida a DHL). https://asest.es/story/comercio-electronico-con-una-menor-tasa-de-devoluciones/
2. flexfulfillment.eu, "7 formas de reducir devoluciones en moda ecommerce": participación de talle/ajuste y descripción en devoluciones de moda. https://www.flexfulfillment.eu/es/7-formas-reducir-devoluciones-moda-ecommerce/
3. Mercado, "CACE: el estudio anual midió $34.033.238 millones en 2025". https://mercado.com.ar/tendencias/comercio-electronico-el-estudio-anual-de-cace-midio-34-033-238-millones-en-2025
4. iProfesional, "Comercio electrónico vs inflación: ¿quién ganó en 2025?": retroceso de indumentaria. https://www.iprofesional.com/tecnologia/447692-comercio-electronico-vs-inflacion-quien-gano-en-2025
5. Cadena 3, sobre Hot Sale 2025 (cifra de tiendas de Tiendanube). https://www.cadena3.com/noticia/el-dato-confiable/que-fue-lo-mas-vendido-en-hot-sale_422993

Todas son fuentes secundarias (prensa y blogs). Hay que reemplazarlas por los informes originales antes de la entrega final.

### Datasets (consultados el 2026-10-06)

6. H&M Personalized Fashion Recommendations (Kaggle). https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations · Espejos: https://huggingface.co/datasets/Qdrant/hm_ecommerce_products y https://huggingface.co/datasets/wbensvage/clothes_desc
7. Fashion Product Images (Kaggle). https://www.kaggle.com/datasets/paramaggarwal/fashion-product-images-dataset · Versión chica: https://huggingface.co/datasets/ashraq/fashion-product-images-small
8. Amazon Reviews 2023 (McAuley Lab). https://amazon-reviews-2023.github.io/ · https://huggingface.co/datasets/McAuley-Lab/Amazon-Reviews-2023
9. Rostamzadeh et al., "Fashion-Gen: The Generative Fashion Dataset and Challenge" (2018). https://arxiv.org/abs/1806.08317
10. DeepFashion-MultiModal. https://github.com/yumingj/DeepFashion-MultiModal
11. Fashionpedia: https://github.com/cvdfoundation/fashionpedia · Fashion200k: https://huggingface.co/datasets/Marqo/fashion200k · MeLi Data Challenge 2019: https://www.kaggle.com/datasets/fredericods/mercado-libre-data-challenge
12. "RA-CoA: Training-free Fashion Image Captioning via Retrieval-Augmented Chain-of-Attributes". https://arxiv.org/html/2609.14100

---

## Bitácora de revisiones

| Fecha | Sección | Qué cambió | Qué lo motivó |
|---|---|---|---|
| 2026-09-28 | Todas | Primera versión | Clase 02, README del repo, búsqueda de proxies de devoluciones y e-commerce |
| 2026-09-28 | Encabezado y sección 3 | Referencia al repo que extendemos (MatLock/UdeSA-computer-vision) | Dejar explícito a qué proyecto se refiere "el repo" |
| 2026-10-06 | Sección 5 | Datasets públicos candidatos, estrategia de datos orgánicos y sintéticos, nueva evidencia y fuentes 6 a 12 | Las ~50.000 imágenes del repo no tienen título ni descripción; búsqueda en Hugging Face, Kaggle y papers |
