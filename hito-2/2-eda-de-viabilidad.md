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
| Volumen (por caso que el producto resuelve) | | |
| Completitud (por columna) | | |
| Corrección (errores, formato, duplicados) | | |
| Vigencia (período que tiene que cubrir) | | |
| Representatividad (grupos que tienen que estar, y en qué proporción) | | |
| Confiabilidad (quién generó y verificó el dato; error de etiquetado tolerable) | | |

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
