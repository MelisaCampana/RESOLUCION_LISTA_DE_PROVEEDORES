# RESOLUCION_LISTA_DE_PROVEEDORES
Este repositorio contiene las listas de artículos de proveedores resueltas y formateadas según los criterios específicos. El objetivo principal es lograr que la "Lista a trabajar" de cada proveedor coincida con el "Modelo/captura" proporcionado, aplicando lógica y las herramientas adecuadas en Google Sheets.

## Herramientas Utilizadas

### 1. **Google Sheets**
- **Google Sheets** fue la herramienta principal utilizada para la importación, limpieza, organización y formateo de los datos. Se emplearon diversas funciones y características de Google Sheets, tales como:
  - **Importación de archivos** (CSV, TXT).
  - **Funciones de texto** (`CONCATENAR`, `DERECHA`, `IZQUIERDA`, etc.) para manipular las columnas.
  - **Formatos numéricos y de moneda** para asegurar que los datos se visualizaran correctamente.
  - **Funciones de ordenación** y **filtrado** para estructurar los datos según el modelo.

### 2. **IA Gemini / ChatGPT**
- Utilicé **Gemini/ChatGPT** para describir y documentar todos los pasos realizados que realicé en **Google Sheets**. La IA me ayudó a estructurar el proceso de manera clara y detallada con el formato necesario para el archivo README.md

--

## Criterios de Archivos Finales

Los archivos finales para cada proveedor cumplen con las siguientes especificaciones:

* **Cabeceras:** Deben tener las cabeceras `Código`, `Descripción` y `Precio` para su correcta identificación.
* **Configuración Regional:** La hoja de cálculo está configurada con la región **Argentina**.
* **Orden de Precios:** Los precios están ordenados de **mayor a menor**.
* **Información Pertinente:** Solo contienen información de los artículos; cualquier dato adicional ha sido eliminado.
* **Archivos Separados:** Cada proveedor tiene su propio archivo final formateado.
* **Solo Valores:** Todas las fórmulas utilizadas han sido eliminadas, quedando únicamente los valores finales.

---

## CASO ANAEROBICO
## Pasos Realizados

### 1. Copia y Conversión del Archivo Original
- Abrí el archivo `Anaerobicos trabajar.xlsx` en **Google Sheets**.
- Guardé una copia del archivo como una **Hoja de Cálculo de Google**:
  - Navegué a **Archivo > Guardar como Hoja de Cálculo de Google**.

### 2. Configuración Regional
- Ajusté la configuración regional de la hoja de cálculo a **Argentina**:
  - Navegué a **Archivo > Configuración**.
  - En la sección "General", seleccioné "Argentina" en el campo **Configuración regional**.
  - Hice clic en **Guardar configuración**.

### 3. Limpieza Inicial de la Planilla
- Eliminé todas las filas y columnas vacías que no contenían información relevante.
- Seleccioné toda la hoja de cálculo (Ctrl+A o Cmd+A) y borré cualquier formato preexistente:
  - Navegué a **Formato > Borrar formato**.
- Ajusté el ancho de las columnas y el alto de las filas para mejorar la visualización.

### 4. Establecimiento de Encabezados
- Verifiqué que los encabezados obligatorios estuvieran presentes y correctamente escritos:
  - "Código", "Producto", "DESC" (Descripción), "Precio Público IVA Incluido", "Precio Minorista sin IVA", "Código de barras".

### 5. Separación de Código y Descripción (Columna Producto Original)
- En la columna "Producto" (originalmente combinada con código y descripción), utilicé el delimitador de cinco espacios para separar los datos.
  - Seleccioné la columna y utilicé la opción **Datos > Dividir texto en columnas** con el delimitador "Personalizado" (cinco espacios).
  - Esto dividió el contenido en dos columnas: **Código** (Columna A) y **Descripción Detallada** (Columna B).

### 6. Recreación de la Columna "Producto" (Unión de Código y Descripción Corta)
- Inserté una nueva columna entre la **Columna A** (Código) y la **Columna C** (Descripción detallada).
- En la nueva columna **Producto**, utilicé la fórmula `=CONCATENAR(A2; " "; C2)` para unir el código con una versión más corta de la descripción.
- Apliqué la fórmula a todas las filas utilizando el relleno rápido (arrastrando la esquina inferior derecha de la celda).
- Reemplacé las fórmulas por valores:
  - Copié y luego pegué solo los valores (Ctrl+Shift+V).

### 7. Ajuste de Formato de Precios
- Seleccioné las columnas correspondientes a los precios: **Precio Público IVA Incluido** y **Precio Minorista sin IVA**.
- Aseguré que el formato de celda fuera de tipo **número** (ej. 1.000,12), el punto como separador de miles y la coma como separador decimal, acorde a la configuración regional de **Argentina**:
  - Navegué a **Formato > Número > Número** (ej. 1.000,12).

### 8. Ordenamiento de Precios
- Seleccioné el rango de datos (sin incluir los encabezados si están congelados) y apliqué un ordenamiento descendente en la columna **Precio Público IVA Incluido**:
  - Navegué a **Datos > Ordenar rango**.
  - Marqué "Los datos tienen fila de encabezado" y seleccioné la columna **Precio Público IVA Incluido** para ordenar de mayor a menor (Z -> A).

### 9. Revisión Final y Exportación
- Realicé una revisión exhaustiva de la hoja final, comparándola con el "Modelo/captura" proporcionado para asegurar que todos los datos y formatos coincidieran.
- Verifiqué que no quedaran fórmulas en ninguna celda.
- Guardé los cambios en la Hoja de Cálculo de Google.
- Finalmente, descargué el archivo en formato `.xlsx` para subirlo a GitHub:
  - Navegué a **Archivo > Descargar > Microsoft Excel (.xlsx)**.

--

## CASO FORD
## Pasos Realizados

### 1. Preparación Inicial en Google Sheets

* **Creación de Hoja:** Se creó una nueva hoja de cálculo para cada proveedor.
* **Importación de Datos:** La "Lista a trabajar" fue importada a la hoja de cálculo.

### 2. Configuración Regional

* Se estableció la configuración regional de la hoja de cálculo a **Argentina** (`Archivo > Configuración de la hoja de cálculo > Configuración regional`).

### 3. Limpieza y Formateo de Datos

* **Identificación de Cabeceras:** Se aseguraron las cabeceras `Código`, `Descripción` y `Precio`.
* **Eliminación de Datos No Pertinentes:** Se eliminaron filas y columnas irrelevantes, dejando solo la información de los artículos.

### 4. Normalización de Códigos

* **Eliminación de Espacios:** Se eliminaron todos los espacios en blanco de los códigos.
    * **Herramienta:** `Editar > Buscar y reemplazar` (buscando " " y reemplazando con "").
    * *(Alternativa con fórmula: `SUSTITUIR(Celda;" ";"")` seguido de un pegado especial de valores).*

### 5. Normalización y Formato de Precios

* **Conversión a Número:** Se aseguró que la columna de `Precio` estuviera formateada como número.
* **Ajuste de Ceros :**
    * Se eliminaron los últimos 4 ceros si el precio original los contenía en exceso (`12340000` -> `1234`).
    * **Herramienta:** División por `10000` (ej. `Celda/10000`) y posterior pegado de valores.
* **Formato Decimal:** Se agregó una coma como separador decimal antes de los últimos dos dígitos (ej. `1234` -> `12,34`), aprovechando la configuración regional Argentina.
    * **Herramienta:** `Formato > Número > Número` (con dos decimales).

### 6. Eliminación de Símbolos

* Se eliminaron los siguientes símbolos de las listas (principalmente de las descripciones):
    * `╝`
    * `┤`
    * `\xE2\x96\x84` (símbolo codificado)
    * `\xE2\x96\x92` (símbolo codificado)
    * **Herramienta:** `Editar > Buscar y reemplazar` para cada símbolo, reemplazando con vacío.

### 7. Ordenamiento Final

* **Ordenamiento por Precio:** Los datos fueron ordenados por la columna `Precio` de mayor a menor.
    * **Herramienta:** `Datos > Ordenar intervalo > Opciones avanzadas de ordenación de intervalo` (orden descendente por la columna Precio).

### 8. Finalización

* **Eliminación de Fórmulas:** Se copiaron y pegaron solo los valores (`Editar > Pegado especial > Pegar solo valores`) para eliminar cualquier fórmula restante.
* **Archivo Final:** Cada archivo `.xlsx` final fue guardado y está listo para ser utilizado.

### 9. Revisión Final y Exportación
- Realicé una revisión exhaustiva de la hoja final, comparándola con el "Modelo/captura" proporcionado para asegurar que todos los datos y formatos coincidieran.
- Verifiqué que no quedaran fórmulas en ninguna celda.
- Guardé los cambios en la Hoja de Cálculo de Google.
- Finalmente, descargué el archivo en formato `.xlsx` para subirlo a GitHub:
  - Navegué a **Archivo > Descargar > Microsoft Excel (.xlsx)**.

---

## CASO HARD
## Pasos Realizados

### 1. Conversión e Importación del Archivo Original (CSV a Google Sheets)
- Creé una nueva **Hoja de Cálculo** en **Google Sheets**.
- Importé el archivo `.csv` proporcionado:
  - Navegué a **Archivo > Importar**.
  - En el cuadro de diálogo de importación, seleccioné **Subir** y cargué el archivo `.csv`.
  - Elegí la opción de importación adecuada para insertar los datos en una nueva hoja o reemplazar la hoja actual, asegurando que el separador fuera detectado correctamente (generalmente "Coma" para archivos CSV o "Detectar automáticamente").

### 2. Configuración Regional
- Ajusté la configuración regional de la hoja de cálculo a **Argentina**:
  - Navegué a **Archivo > Configuración de la hoja de cálculo**.
  - En la sección **General**, seleccioné "Argentina" en el campo **Configuración regional**.
  - Hice clic en **Guardar configuración**.

### 3. Limpieza Inicial de la Planilla
- Eliminé todas las filas y columnas vacías que no contenían información relevante.
- Seleccioné toda la hoja de cálculo y borré cualquier formato preexistente:
  - Navegué a **Formato > Borrar formato**.
- Ajusté el ancho de las columnas y el alto de las filas para mejorar la visualización de los datos.
- Verifiqué y establecí los encabezados obligatorios de acuerdo al modelo:
  - "EMPRESA", "CÓDIGO", "DESCRIPCION", "DESCRIP2", "ORIGINAL", "PRECIO", "PRECIO FINAL", "MARCA", "LISTA", "NOV", "STOCK", "INDU", "RUBRO", "DTO".

### 4. Corrección de Precios (Columna **PRECIO FINAL**)
- La columna de **PRECIO** (Columna F) contenía dígitos extra separados por un punto (ej. 729751.37). El objetivo era corregir el precio y reflejarlo en la columna **PRECIO FINAL** (Columna G).
  
#### 4.1. Duplicación de la Columna:
- Para trabajar de manera segura, duplicé la columna original de precios (**Columna F**).

#### 4.2. División de Texto para Eliminación de Decimales:
- En la columna duplicada, seleccioné el rango de precios y utilicé la herramienta **Datos > Dividir texto en columnas**.
  - Utilicé el punto (.) como delimitador para separar los valores.
  - Esto dividió la columna en dos: una con la parte entera del precio y otra con los dígitos extra.

#### 4.3. Eliminación de Dígitos Extra:
- Eliminé la columna que contenía los dígitos extra.

#### 4.4. Aplicación de Formato Numérico:
- Apliqué el formato de **moneda** (con dos decimales y separador de miles) a la columna restante (parte entera del precio).
  - Navegué a **Formato > Número > Número** (ej. 1.000,12).

#### 4.5. Eliminación de Puntos en la Columna Original:
- Si trabajé sobre la columna original (**Columna F**), eliminé los puntos de miles mediante:
  - **Edición > Buscar y reemplazar**, reemplazando todos los puntos (.) por "nada" ().
- Luego, apliqué el formato numérico adecuado para interpretar los valores como números enteros.

#### 4.6. Verificación:
- Verifiqué que la columna **PRECIO FINAL** reflejara los precios correctos del modelo.

### 5. Ordenamiento de Precios
- Seleccioné todo el rango de datos de la tabla (sin incluir los encabezados) y ordené los precios de mayor a menor basándome en la columna **PRECIO FINAL**:
  - Navegué a **Datos > Ordenar rango**.
  - Marqué **"Los datos tienen fila de encabezado"**.
  - Seleccioné la columna **PRECIO FINAL** y elegí el orden **Z -> A** (descendente).
  - Hice clic en **Ordenar**.

### 6. Aplicación de Formato de Colores Alternos
- Seleccioné todas las celdas con datos de la tabla.
- Navegué a **Formato > Colores alternos**.
- En el panel lateral, seleccioné el estilo de color que coincidía con el modelo proporcionado, aplicando las bandas de colores a las filas.

### 7. Revisión Final y Exportación
- Realicé una revisión exhaustiva de la hoja, comparándola con el "Modelo/captura" para asegurarme de que los datos, formatos y el orden coincidieran exactamente con los requisitos.
- Me aseguré de que todas las fórmulas utilizadas fueran eliminadas, dejando solo los valores finales en las celdas:
  - Seleccioné las columnas con fórmulas, las copié y luego pegué solo los valores en el mismo lugar.
- Guardé los cambios en la **Hoja de Cálculo de Google**.
- Finalmente, descargué el archivo en formato `.xlsx`:
  - Navegué a **Archivo > Descargar > Microsoft Excel (.xlsx)**.

---

## CASO RASA
## Pasos Realizados

### 1. Conversión e Importación del Archivo Original (TXT a Google Sheets)
- Creé una nueva **Hoja de Cálculo** en **Google Sheets**.
- Importé el archivo `.txt` proporcionado:
  - Navegué a **Archivo > Importar**.
  - En el cuadro de diálogo de importación, seleccioné **Subir** y cargué el archivo `.txt`.
  - Configuré las opciones de importación para que los datos se dividieran correctamente en columnas, teniendo en cuenta los delimitadores o anchuras fijas en el archivo TXT (por ejemplo, **"Detectar automáticamente"** o especificando un delimitador si es visible, o **"Ancho fijo"** si los datos no tenían un separador claro pero sí posiciones fijas de inicio/fin).

### 2. Configuración Regional
- Ajusté la configuración regional de la hoja de cálculo a **Argentina**:
  - Navegué a **Archivo > Configuración de la hoja de cálculo**.
  - En la sección **General**, seleccioné **Argentina** en el campo **Configuración regional**.
  - Hice clic en **Guardar configuración**.

### 3. Limpieza Inicial de la Planilla
- Eliminé todas las filas y columnas vacías que no contenían información relevante.
- Seleccioné toda la hoja de cálculo y borré cualquier formato preexistente:
  - Navegué a **Formato > Borrar formato**.
- Ajusté el ancho de las columnas y el alto de las filas para mejorar la visualización de los datos.
- Establecí los encabezados de las columnas para que coincidieran con el modelo y el caso anterior:
  - **"ARTICULO", "DESCRIPCION", "PRECIO", "AUX"**.

### 4. Unión de Código y Descripción (Columna **"ARTICULO"** y **"DESCRIPCION"**)
- Se identificó la necesidad de crear una columna unificada que combine el código (Columna A) y la descripción (Columna B).
- Inserté una nueva columna (**Columna C**).
- En la primera celda de esta nueva columna (ej. C2), utilicé la fórmula `=CONCATENAR(A2; " "; B2)` para unir el código de la Columna A con la descripción de la Columna B, separados por un espacio.
- Apliqué esta fórmula al resto de las filas utilizando la función de relleno rápido.

#### 4.1. Limpieza de Fórmulas:
- Copié el contenido de la columna y luego pegué solo los valores en el mismo lugar para eliminar las fórmulas:
  - Utilicé Edición > Pegado especial > Pegar solo valores.

### 5. Eliminación de Caracteres Específicos
- Eliminé caracteres especiales (→, 伃, 厲) que podían estar presentes en la lista de artículos.
- Utilicé la función **Buscar y reemplazar** (Ctrl+H o Cmd+H):
  - En el campo **Buscar**, pegué cada caracter (→, 伃 o 厲).
  - En el campo **Reemplazar con**, dejé el campo vacío.
  - Seleccioné el rango apropiado (generalmente toda la hoja o las columnas de texto relevantes).
  - Hice clic en **Reemplazar todos**.

#### 5.1. Eliminación de Caracteres Finales:
- También eliminé los tres caracteres finales que aparecían al final de la descripción de algunos artículos y que no formaban parte de la descripción real del producto. Esto se realizó utilizando **Buscar y reemplazar** el patrón era consistente.

### 6. Extracción y Formato del Precio
- Analicé la **Columna D**, que contenía un número extenso que incluía el precio.
- Identifiqué que los últimos 11 dígitos de este número correspondían al precio del producto.
- Creé una nueva columna a la derecha de la **Columna D**.
- En esta nueva columna, utilicé la fórmula `=DERECHA(D2; 11)` para extraer los últimos 11 dígitos de cada celda de la **Columna D**.
- Apliqué esta fórmula al resto de las filas.

#### 6.1. Formato de Número para el Precio:
- Seleccioné la columna con los precios extraídos y apliqué el formato numérico necesario para visualizarlo correctamente como **moneda** con separador de miles y dos decimales:
  - Navegué a **Formato > Número > **Número** (ej:1.000,12)

### 7. Ajuste de la Columna D (Código de Referencia/Adicional)
- La **Columna D** original, después de extraer el precio, aún contenía otros dígitos.
- Comparando con el modelo, esta columna debía tener 14 dígitos que representaban otro código o referencia.
- Creé otra columna a la derecha.
- Utilicé la fórmula `=IZQUIERDA(D2; 14)` para extraer los primeros 14 dígitos de la **Columna D** original.
- Luego, eliminé la **Columna D** original, ya que ya no era necesaria.

### 8. Ordenamiento de Precios
- Seleccioné todo el rango de datos de la tabla (sin incluir los encabezados) y ordené los precios de mayor a menor basándome en la columna **PRECIO**:
  - Navegué a **Datos > Ordenar rango**.
  - Marqué **"Los datos tienen fila de encabezado"**.
  - Seleccioné la columna **PRECIO** y elegí el orden **Z -> A** (descendente).
  - Hice clic en **Ordenar**.

### 9. Ajuste y Formato de la Columna F (Cantidad/Stock - "AUX")
- Basándome en el modelo, interpreté que la **Columna F** contenía una **cantidad de stock**
- Ajusté el formato de esta columna para que coincidiera visualmente con el modelo:
  - Apliqué formatos numéricos.
  - Aseguré que los asteriscos (*) se mantuvieran o se añadieran si formaban parte del formato del modelo.

### 10. Limpieza de Fórmulas Final
- Para garantizar que el archivo final solo contenga valores y no fórmulas, seleccioné todas las columnas con fórmulas.
- Copié el contenido (Ctrl+C o Cmd+C).
- Pegué solo los valores en el mismo lugar Edición > Pegado especial > Pegar solo valores).

### 11. Revisión Final y Exportación
- Realicé una revisión exhaustiva de la hoja, comparándola con el "Modelo/captura" para asegurarme de que los datos, formatos y el orden coincidieran exactamente con los requisitos.
- Verifiqué que los encabezados fueran correctos y que no hubiera información superflua.
- Guardé los cambios en la **Hoja de Cálculo de Google**.
- Finalmente, descargué el archivo en formato `.xlsx`:
  - Navegué a **Archivo > Descargar > Microsoft Excel (.xlsx)**.

