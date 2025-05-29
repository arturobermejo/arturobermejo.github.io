---
title: "Mi camino a entender (por fin) los LLMs: Relaciones y funciones"
date: 2025-03-06
draft: false
author: "Arturo Bermejo"
tags: ["tecnología", "llms", "inteligencia artificial"]
language: "es"
post_id: "llms-my-learning-way-part-1"
slug: "mi-camino-entender-llms-relaciones-y-funciones"
lang_link: "/blog/my-learning-path-llms-relations-and-functions/"
---

![relaciones y funciones](/images/llms-my-learning-way-part-1.jpg)

Nuestra vida diaria está llena de variables que depende unas de otras, desde cómo la calidad del sueño afecta a tu salud hasta cómo el clima afecta tu estado de ánimo. Esencialmente, se trata de cómo las cosas se conectan e influyen entre sí.

La inteligencia artificial se suele percibir como un tema muy abstracto, pero podríamos argumentar que en el fondo todo se trata de estas mismas relaciones de dependencia: cómo los datos se conectan, cómo los patrones emergen y cómo los resultados se obtienen a partir de ellos. Por lo tanto es muy útil partir de entender cómo se fundamentan y representan esas relaciones para comprender como funcionan los modelos de inteligencia artificial.

Aunque las matemáticas pueden parecer intimidantes, al verlas en contexto se convierten en una herramienta fundamental para comprender e internalizar mejor las ideas. En ese sentido el concepto de función es la base para representar estas relaciones, de manera numérica y precisa. Una función entonces nos permite modelar la relación entre una o más variables independientes y una variable dependiente.

Imaginemos que queremos entender cómo nuestra felicidad depende de dos factores: la cantidad de amigos que tenemos y la cantidad de dinero que poseemos. Para representar esta relación, podemos utilizar una función matemática.

Por ejemplo, consideremos la siguiente función:

\[
f(x, y) = 2x + 5y
\]

Donde:
- x: representa la cantidad de dinero.
- y: representa la cantidad de amigos.
<br><br>

Esta función nos dice que nuestra felicidad se ve influenciada tanto por el dinero como por los amigos, pero en distinta medida. Según esta fórmula, cada unidad de dinero suma 2 puntos a la felicidad, mientras que cada amigo suma 5 puntos. En otras palabras, la función sugiere que los amigos tienen un impacto mayor en la felicidad que el dinero.

El concepto de función es clave porque nos permite modelar relaciones de dependencia en distintos contextos. Siempre que una o más variables influyan en un resultado, una función puede ayudarnos a representarlo de manera precisa y comprensible.

### El problema de la generación de texto

En los modelos como GPT también encontraremos estas relaciones. Estos modelos podemos verlos como funciones, cuyo objetivo es predecir o generar una palabra en base a otra lista de palabras previas, es decir predecir la palabra siguiente de una frase de manera coherente.

Por ejemplo, si tenemos la frase:

> “El cielo es…"

podríamos esperar que la siguiente palabra generada sea "azul", aunque también podrían surgir otras opciones como "gris" o "nublado", dependiendo del contexto de la oración actual.

En realidad en este proceso, el modelo no trabaja únicamente con palabras completas, sino con tokens, que pueden representar una palabra, una parte de una palabra o incluso un símbolo, pero por ahora consideremos que son palabras.

Entonces podemos ver que existe una relación de dependencia entre la frase dada y la palabra a generar, la cual podemos representar con la siguiente notación matemática que corresponde a una función:

\[
\text{siguiente_palabra} = f(\text{frase})
\]

Aunque parezca que es una simplificación muy drástica, al final del día es simplemente una función. No es una función sencilla claramente pero una función al fin y al cabo.

Ahora preguntémonos: ¿De qué más depende la capacidad de un modelo para generar la siguiente palabra de manera óptima?

Podemos intuir que depende de dos componentes fundamentales:

1. **La frase actual**, como ya vimos, proporciona el contexto inmediato y define las posibles palabras que pueden seguir.

2. **El conocimiento del lenguaje**, entendido como el conjunto de reglas y patrones que el modelo “conoce”. Esto incluye la gramática, la estructura de las oraciones, el significado de las palabras (semántica) y la relación entre conceptos.

Por ejemplo, si tenemos la frase:

> "Hoy llevo paraguas porque el cielo está…"

el modelo debe analizar la estructura y significado de la oración, pero también aplicar su conocimiento previo sobre el clima y el uso del lenguaje para predecir palabras como "nublado" o "lluvioso", en lugar de algo sin relación como "feliz".

Podemos ver entonces dos elementos que trabajan juntos: la frase actual define el contexto inmediato, mientras que el conocimiento guía la selección de la palabra más adecuada.

Con esta idea en mente, podemos modificar nuestra función para reflejar que la generación de la siguiente palabra no solo depende de la frase actual, sino también del conocimiento previo del lenguaje:

\[
y = f(x, w)
\]

Donde:
- \(x\): representa la frase u oración actual.
- \(w\): es el conocimiento del lenguaje.
- \(y\): es la siguiente palabra generada.
<br><br>

Este mismo principio se puede aplicar en muchos otros escenarios donde una decisión depende tanto de la información presente como del conocimiento acumulado.

Tomemos como ejemplo una partida de ajedrez. Nuestro próximo movimiento no solo depende de las jugadas que han ocurrido en la partida actual (x), sino también de nuestro conocimiento previo sobre estrategias, aperturas y patrones de juego (w). Este conocimiento nos permite evaluar qué movimientos (y) son más favorables y cuáles podrían llevarnos a una desventaja.

### Un primer modelo

Con los conceptos que hemos visto hasta el momento pensemos, ¿Y ahora cómo puedo definir mi modelo?

Dado que x es la entrada y y la salida de nuestro modelo, solo hay dos aspectos que podemos definir para nuestro modelo:

- El valor o valores de w, que representa el conocimiento del modelo.
- La forma de la función, que define cómo interactuan x y w para generar la salida.
<br><br>

La forma función es la estructura del modelo, lo que podríamos llamar “la arquitectura”, que serian simplemente las operaciones matemáticas que conforman este modelo. Es decir la función podría estar compuesta de muchas otras funciones internamente.

Pero, ¿Cómo encontramos los valores adecuados para w? Aquí es donde entra en juego el concepto de entrenamiento. Entrenar un modelo significa ajustar los valores de w de manera progresiva, basándonos en ejemplos previos, hasta que el modelo logre hacer predicciones acertadas. Es decir para obtener ese “conocimiento” del que hablábamos.

Durante el entrenamiento, w no es fijo; es un conjunto de valores que iremos ajustando para que el modelo pueda hacer mejores predicciones. Pero una vez entrenado el modelo este valor de w es fijo para la predicción de la siguiente palabra, pues ya se considera óptimo para cualquier valor de x.

Por ahora pensemos w como valores que podemos modificar arbitrariamente.

Aterrizamos matematicamente lo que hemos comentado hasta ahora.

Habíamos dicho que nuestro modelo se define como:

\[
y = f(x, w)
\]

Pero hay un problema: las funciones matemáticas trabajan con números, mientras que el lenguaje está compuesto por palabras. Para poder operar matemáticamente, necesitamos encontrar una forma de representar las palabras como números.

Una forma sencilla de hacer esto es asignar un identificador numérico a cada palabra de un conjunto determinado. Por ejemplo:

azul → 227 <br>
cielo → 350 <br>
frío → 402 <br>
el → 578 <br>
es → 698 <br>

Ahora, podemos redefinir nuestra función para operar con estas representaciones numéricas. Asumimos por ahora que nuestro modelo ya es óptimo por lo que los parámetros w son constantes.

\[
f(x_1, x_2, x_3) = x_1 w_1 + x_2 w_2 + x_3 w_3
\]

Aquí, usamos tres palabras de entrada

\[
x_1, x_2, x_3
\]

y tres valores asociados de conocimiento

\[
w_1, w_2, w_3
\]

que actuarán como pesos en la función, asignándole mayor influencia a una palabra u otra.

Vamos a calcular el resultado con los siguientes valores:

\[
w_1 = 1
\]
\[
w_2 = 1.5
\]
\[
w_3 = 0.5
\]

Si tomamos la frase "El cielo es", sus valores serían:

\[
x_1 = 578
\]
\[
x_2 = 698
\]
\[
x_3 = 350
\]

Sustituyéndolos en nuestra función:

\[
\begin{align*}
f(578, 350, 698) &= 578 \times 1 - 350 \times 1.5 + 698 \times 0.5 \\
                 &= 578 - 525 + 349 \\
                 &= 402
\end{align*}
\]

El resultado es 402, que en nuestra lista de palabras corresponde a "frío", formando la frase:

> "El cielo es frío"

Ahora, probemos otro conjunto de pesos, cambiando w_2 por 2.0 en lugar de 1.5:

\[
\begin{align*}
f(578, 350, 698) &= 578 \times 1 - 350 \times 2.0 + 698 \times 0.5 \\
                 &= 578 - 700 + 349 \\
                 &= 227
\end{align*}
\]

El resultado ahora es 227, que corresponde a la palabra "azul", formando la frase:

> "El cielo es azul",

lo cual parece una mejor elección en este contexto.

Este ejemplo nos muestra cómo la elección de los valores w afecta la palabra generada. Si encontramos los valores correctos, el modelo puede generar frases más coherentes. Esto se logra a través del proceso de entrenamiento.

Este ejemplo ha sido principalmente ilustrativo, ya que podemos notar muchos inconvenientes de este modelo, pero es a partir de estos problemas que vamos a ir justificando porque añadimos cada nuevo concepto.

Algunos de los problemas que podemos ver:

- Generalización insuficiente: Los valores de w que usamos en el ejemplo fueron escogidos de manera arbitraria y no funcionan para todas las secuencias de palabras posibles.

- Correspondencia numérica: El número resultante de la función podría no coincidir con ningún identificador asignado, lo que complicaría la conversión de nuevo a una palabra.

- Falta de variabilidad: Si el modelo siempre genera la misma palabra para una secuencia dada, pierde la capacidad de ser creativo o adaptarse a contextos variados. En la práctica, un poco de aleatoriedad es deseable para capturar la diversidad del lenguaje.
</br>

Dejo un ⮕ [jupyter notebook](https://github.com/arturobermejo/llms-from-scratch/blob/main/part1.ipynb) donde podemos ver una implementación en Python de lo que hemos visto.

En siguientes posts veremos los conceptos relacionados a entrenamiento, redes neuronales, embeddings y transformers.
