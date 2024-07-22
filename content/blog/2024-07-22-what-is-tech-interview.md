+++
title = "what is a technical interview"
date = 2024-07-22
draft = false
 

[taxonomies]
categories = ["culture"]
tags = ["culture"]

[extra]
lang = "en"
toc = true
show_comment = true
math = false
mermaid = false
+++
---

Y como sacar buena nota.

# How to score a good mark

Cientos de personas me suelen contactar para pedirme ayuda cuando tienen que hacer una práctica para la universidad o una prueba de trabajo. Me dicen este es el enunciado, qué me recomiendas? No sé qué tengo que hacer para pasar la prueba! Entiendo la confusión por dos motivos principales.

## La confusión

### Primer motivo de confusión

Mucha gente, con poca experiencia aún en la industria, piensa que las pruebas de programación sirven para encontrar **buenos candidatos** para un puesto de trabajo. No es cierto. El objetivo para la empresa es encontrar un pica código con las neuronas justitas para hacer el trabajo sucio pagándole el mínimo dinero posible. Para estas posiciones, los procesos suelen tener múltiples pasos y pruebas técnicas: algoritmia, estructuras de datos, teoría, system design...

Ahora, todo el mundo con experiencia suficiente en la industria sabe que encontrar a un buen ingeniero es fácil porque solo requiere cuatro sencillos pasos:

Encontrar a una persona y que esta persona sea ingeniero. Hablar 5-10 minutos con esta persona. Una conversación de 5-10 minutos es suficiente para cualquier buen ingeniero para determinar si otra persona tiene las capacidades técnicas necesarias para el puesto. Ofrecer al ingeniero una oferta atractiva. Que este ingeniero quiera trabajar contigo. Porque una entrevista funciona en ambas direcciones y una conversación también.

### Segundo motivo de confusión

Las pruebas son ambiguas. Dejan espacio a la interpretación del lector. Normalmente, quien escribió el enunciado tampoco tenía mucha idea de lo que pedía... Y raramente sabría el mismo resolverlo.

Aclaración necesaria realizada. Es importante antes de poder resolver una duda y dar una respuesta, entender la propia pregunta. Si no entiendes la pregunta no podrás entender nunca la respuesta. Tras esta fascinante deconstrucción del mundo corporativo podemos avanzar. 

## La pre-prueba

Antes de hacer una prueba hay que realizar un paso previo. Y es el más difícil que vas a realizar en tu vida. Un difícil acto de sinceridad y honestidad propio. Evaluar "objetivamente" nuestro nivel. 

Queremos trabajar haciendo algo, podemos hacerlo? Si la respuesta es no, en un mundo donde se busquen buenos candidatos no habría manera de que pases ningún proceso. Por suerte o desgracia, en el mundo real, puedes mentir y estudiar lo necesario para terminar moviendo tests unitarios en una gran empresa sin mucha dificultad y mantener código escrito por influencers de Tiktok y Twitch. Lo siento mucho por este bache en tu vida, y espero que si estás aquí, algún día puedas salir de esa mierda.

## La prueba

La prueba técnica es junto a la conversación de 5-10 minutos, la manera más fiable, simple y fácil de determinar el nivel de un ingeniero. Si no lo entiendes es porque aún no eres un buen ingeniero. Por eso me lo preguntas y por eso no sabes qué hacer para pasar pruebas. Pero no te desanimes porque todos hemos pasado por ahí en algún momento en nuestra vida. Algunos incluso han pasado por el bache de la deshonestidad y han terminado en alguna jaula de oro odiando su existencia a diario. Lo importante es que después de la tormenta sale el arcoiris, y [si tienes las cualidades de un buen ingeniero](https://arnaudiaz.com/blog/traits-good-programmer/) algún día saldrás de ahí.

Si crees con honestidad que tienes los conocimientos y cualidades de un buen programador, vamos a realizar una prueba y te voy a guiar en el proceso. De hecho, recuerda siempre que estés programando y tengas una duda que no estás solo. Puedes contar conmigo. Cuando creas que no eres lo suficientemente bueno o que estás escribiendo código caca puedes pensar en mí. Imagínate que estoy sobre tu hombro y te estoy gritando: si eres un paquete, dedícate a otra cosa pero por favor deja de programar. Seguramente ambos estemos en lo cierto y estés escribiendo caca, deja de escribir código caca.

### Junior

Voy a hacer algo que no me gusta, que es utilizar estos pseudo-rangos que usan las empresas para dividir a los compañeros. Ya sabéis que yo respeto y valoro a todos los compañeros independientemente de su nivel o rol en el equipo. Seas un Product Manager o un DevOps recién salido de la universidad, si estás en mi equipo es porque tienes algo que aportar. En este caso, veamos qué puede aportar alguien que acaba de empezar.

El único objetivo de una prueba técnica a este nivel es el siguiente: QUE FUNCIONE. DEMOSTRAR QUE SABES PROGRAMAR.

No hay que pensar más en ello porque este es el primer paso que todo ingeniero y programador debe completar en su día a día. Que lo que haga funcione. El objetivo es simple, la realidad es que la mayoría de programadores no saben aún programar y su código no funciona. Tu objetivo es demostrarme que sabes hacer código que funciona y me lo demuestres.

Imagina que te pido que me hagas un código que lea un archivo y me cuente las veces que aparecen las palabras en ese archivo y me lo ordenes. Me da igual qué lenguaje uses, qué paradigma, si haces TDD o Arquitectura Hexagonal Chupiguay al cuadrado, no te estoy pidiendo nada de ese buzz wording para Tiktokers. Te pido que el código funcione.

- Resuelve el ejercicio
- Escribe unos tests que yo pueda fácilmente validar
- Asegúrate de que tu código se puede compilar y ejecutar de manera simple 
  - Aquí puedes utilizar Github Actions o similares si quieres

Fíjate que no estoy entrando en ningún detalle, porque los detalles me dan igual. Solucionar un problema y que funcione ya es un nivel de dificultad que la gran mayoría de programadores no será capaz de realizar, te lo aseguro. He entrevistado chavales recién salidos de la universidad a los que les pedía hacer el típico for loop de Fibonacci, me decían que lo harían en Haskell porque sacaron un 10 en la asignatura, y no consiguieron en 1 hora hacer que el código compilase...

Si es una prueba con el entrevistador al lado y quieres impresionar al entrevistador, por favor, no me hagas perder mucho el tiempo y resuélvelo sin darme dolores de cabeza. Porque tengo otras cosas que hacer, como irme a la piscina ahora en verano después de comer, y estoy ocupando la tarde contigo.

Cuando un compañero entra al equipo, da igual el nombre que ponga en su Slack: junior, mid, senior o rockstar developer. Lo único que le vamos a pedir es que el código que escriba funcione.

### Mid

El siguiente paso es el que se esperaría de una persona que ha trabajado en la industria. Comparado con la gente que nunca lo ha hecho. Y ojo, aquí me gustaría dejar algo claro. Esto incluye a gente que lleva trabajando 1 año y gente que lleva trabajando 40 años como programador. Como dicen los sabios:

> 1 año de experiencia 20 veces, no son 20 años de experiencia.

La gran mayoría de programadores suele quedarse en este rango para el resto de sus vidas. Y aquí hay que decir que no hay nada malo con ello. Estamos hablando de "profesionales capaces" que además pueden formar a otros ingenieros noveles como los que vimos en el paso anterior.

Volviendo a la prueba. El mayor error que cometen los programadores en este nivel es olvidarse del paso número uno. Que el código funcione y saber programar. Que el código funcione es programar la solución al problema que te piden. La mayoría de gente no sabe programar, y durante años hacen malas soluciones. Esto provoca que pierdan la humildad y la sinceridad y no sean honestos. Se piensan que saben lo que hacen, y algunos aun peor, se creen que lo que hacen está bien. Por lo general, nos encontramos con candidatos que se pierden en los detalles irrelevantes, en las arquitecturas, en los procesos que no solucionan problemas sino que generan nuevos problemas, en las supuestas buenas prácticas que han aprendido, candidatos que han leído cuatro libros de Clean Code y se han olvidado que lo más importante es hacer que el código funcione. 

Objetivos de la prueba:

- Cumplir con los requisitos del paso anterior: saber programar.
- Demostrar que sabes programar... en el mundo real.

El mundo de fantasía en que viven estudiantes y gurús de software que publican libros de buenas prácticas de programación, no tiene nada que ver con el mundo real. En el mundo de fantasía, se resuelven problemas de fantasía. En el mundo real, resolvemos y nos encontramos con problemas reales. El objetivo de esta prueba es demostrar que conoces estos problemas y resolver algunos en la prueba. Menciónalos durante la conversación de 5-10 minutos.

Volviendo al caso de contar palabras de un archivo. Fíjate qué ejemplo más simple estoy usando, y fíjate cómo lo podemos usar en todos los niveles.
Seguramente te vas a encontrar con que las cosas en el mundo real fallan. Vas a tener caracteres raros, archivos corruptos, algún quinceañero con granos en la cara te intentará meter un XSS para hacer la bromita. Cuando las cosas se rompen tienes que debugar, necesitas sacar métricas y logs básicos del producto. Estos procesos consumirán CPU y MEM, necesitarás tener unos conocimientos de hardware y de cómo provisionar.

Todo esto desde el punto de vista técnico. Un ingeniero capaz seguramente le interesa trabajar para una empresa capaz, durante la entrevista lanzará muchas preguntas y estará encantado de revisar el código de sus futuros compañeros si está en GitHub disponible. Una entrevista, como hemos comentado, funciona en ambas direcciones. Y para la mayoría de buenos ingenieros que saben programar y saben programar en el mundo real, que su equipo también cumpla estas cualidades es crucial. Y como he comentado, la gran mayoría de ingenieros no sabe programar. En este punto, lo más normal es que rechaces más entrevistas de las que aceptas, y es probable que rechaces muchas empresas si no te dan buena espina.

### Niveles superiores en la jerarquía burocrática de tu empresa

Los siguientes niveles en general suelen ser ingenieros que cumplen los dos pasos anteriores. Sabes programar, sabes programar en el mundo real. Y es aquí donde el tener experiencia entra en juego. Pero hay distintos perfiles. Según donde hayas acumulado experiencia en tu vida, tendrás unas características que te pondrán por encima del resto del mundo.

El proceso es exactamente igual que el anterior, te daré un objetivo simple, resuélvelo. Enséñame que sabes programar, que sabes programar en el mundo real y demuestra por qué te mereces más dinero que el resto porque sabes hacer cosas que el resto no sabe.

La verdad, no hay muchos ingenieros así en el mundo. Y si lo eres, no necesitas mi ayuda.

## Conclusión

Si habéis llegado al final. Enhorabuena. La conclusión es leerte el texto de arriba.