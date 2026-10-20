# EDA de viabilidad

**Documento 2 de 4 del Hito 2**

---

**Equipo:** Jorge Federico Flores, Nicolás Velázquez, Nilayvi Barrientos, Rubén Ortigoza

**Muestra** (ruta en el repo): [`data/muestra/`](../data/muestra/) en [MatLock/UdeSA-toi](https://github.com/MatLock/UdeSA-toi). Son los CSV de `img-puller` del prototipo [MatLock/UdeSA-computer-vision](https://github.com/MatLock/UdeSA-computer-vision)

**Notebook** (ruta en el repo): [`notebooks/eda_viabilidad.ipynb`](../notebooks/eda_viabilidad.ipynb)

---

## 1. Requerimientos: el nivel que el producto necesita

| Propiedad | Nivel que el producto necesita | De dónde sale ese nivel |
|---|---|---|
| Volumen (por caso que el producto resuelve) | ≥ 100 ejemplos por clase en cada atributo que el producto devuelve, de los que ≥ 30 por clase se puedan reservar para el conjunto de evaluación. Las clases que no llegan se agrupan en "otro" o quedan fuera del alcance | El producto devuelve un valor por atributo con su confianza ([canvas](../canvas.md), sección 3), y la métrica técnica es un F1 por atributo (canvas, sección 6): sin casos de cada clase en evaluación no se puede estimar. El prototipo ya usa `min_samples_per_class: 20` como piso de entrenamiento |
| Completitud (por columna) | ≥ 98 % de valores presentes en cada columna de etiqueta. ≥ 95 % de `image_url` que responden y abren como imagen. Además, la muestra tiene que traer los atributos que el producto prioriza: tipo de prenda y color | Canvas, sección 3 (Juicio): tipo de prenda y color son los campos que más reclamos generan, y por eso llevan el umbral más exigente. Una imagen que no abre es una fila que no sirve ni para entrenar ni para evaluar |
| Corrección (errores, formato, duplicados) | 0 duplicados exactos de `id`. ≤ 1 % de imágenes duplicadas (exactas o casi exactas). 0 valores fuera de la taxonomía de cada atributo. ≤ 10 % de etiquetas incorrectas al cotejarlas a mano contra la foto | Canvas, sección 6: si la persona modifica más del 20 % de los campos, la herramienta no ahorra nada. Un 10 % de etiquetas erróneas ya consume la mitad de ese margen antes de que el modelo se equivoque |
| Vigencia (período que tiene que cubrir) | Productos publicados en los últimos 5 años (2021 en adelante) | La moda cambia por temporada: un catálogo de hace más de 5 años describe otras prendas y otros cortes que los que carga hoy una marca. *(H: el umbral de 5 años es nuestro)* |
| Representatividad (grupos que tienen que estar, y en qué proporción) | Que estén las categorías que carga una marca argentina chica (remeras y tops, pantalones, calzado, vestidos, abrigos), cada una con ≥ 10 % de la muestra. Fotos tipo catálogo, con y sin modelo, parecidas a las de esas marcas | Canvas, sección 1 (a quién le pasa) y sección 7 (calidad de servicio: el sistema anda peor fuera de las clases de entrenamiento y con fotos distintas) |
| Confiabilidad (quién generó y verificó el dato; error de etiquetado tolerable) | Coincidencia entre dos personas que re-etiquetan por separado la misma muestra chica: ≥ 80 % y κ de Cohen ≥ 0,6 por atributo. Coincidencia entre la etiqueta original y el consenso del equipo: ≥ 90 % | Dos personas que etiquetan por separado es la forma de medir el error de etiquetado (material de la Clase 3); κ ≥ 0,6 es el umbral usual de acuerdo "sustancial". El 90 % es el complemento del ≤ 10 % de error de Corrección |

## 2. Resultados de la verificación

| Propiedad | Medido o estimado | Resultado (número o gráfico) | Celda del notebook | Si es estimado, procedencia y qué haría falta para medirlo | Cumple el nivel |
|---|---|---|---|---|---|
| Volumen | | | | | |
| Completitud | | | | | |
| Corrección | | | | | |
| Vigencia | | | | | |
| Representatividad | | | | | |
| Confiabilidad | | | | | |

## 3. Exposición al *leakage*

| Búsqueda | Qué se busca | Resultado (número) | Celda del notebook |
|---|---|---|---|
| La definición | Columnas que se completan después del momento en que el producto tendría que predecir | | |
| El tiempo | Si hay fecha y la etiqueta depende del momento | | |
| Los duplicados | Exactos y casi exactos | | |
| Los grupos | Varias filas de una misma persona, cliente u objeto | | |
| La generación | Cómo se produjo cada dato; se le pregunta a quien lo conoce | | |
