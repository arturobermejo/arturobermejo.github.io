---
title: "Interfaces Conversacionales y Chatbots"
date: 2016-10-26
draft: false
author: "Arturo Bermejo"
tags: ["tecnología", "chatbots", "inteligencia artificial", "interfaces"]
---

Las interfaces gráficas son las que predominan hoy en día, pero siempre me ha frustrado maquetar-programar interfaces para proyectos web, ya sea por la compatibilidad entre navegadores o la cantidad de frameworks frontend de moda que surgen.

Por otro lado, cuando me adentré en el desarrollo móvil, me pareció un poco más estable, ya que al ser la pantalla de menor tamaño te mantenía enfocado en colocar lo realmente importante. Pero dentro del mundo móvil es notable que la mayoría de personas rara vez instala alguna aplicación nueva o la mantiene instalada. Esto puede ser por muchos motivos, pero la acción de instalar-probar-desinstalar una app es bastante trabajo, a veces solo necesitamos usar algo una sola vez, además de que muchas de ellas son poco útiles, debido a la idea de crear una app para todo.

Pero a pesar de que las interfaces gráficas y las apps predominen hoy ¿Son la mejor forma para interactuar con los servicios que usamos diariamente?.

Las apps de mensajería ya sobrepasaron en uso a las apps de redes sociales como lo muestra el siguiente gráfico.

![Gráfico que verás en todos los artículos sobre chatbots](/images/chatbot-stats.png)

*Gráfico que verás en todos los artículos sobre chatbots*

Desde el principio de los tiempos el lenguaje ha sido la forma más natural de expresar nuestras intenciones, y ya que tanto tiempo pasamos en ello _¿No deberían muchos de los servicios que usamos diariamente adaptarse a ese medio?_ _¿No debería ser el lenguaje nuestra principal interfaz?_

La respuesta aún no es del todo clara, pero muchas de las grandes empresas están empezando a apostar por ello y por lo cual este año ha habido bastante revuelo con el tema de los chatbots y las interfaces conversacionales.

El evento F8 de este año fue el punto de quiebre, Facebook abría su plataforma de Messenger para la integración de bots, y con ello voces dentro de las empresas más importantes hacían de este tema la nueva tendencia, la próxima revolución.

Actualmente existen varias plataformas que soportan la integración de bots, tales como Telegram, Slack, Skype, Line y Messenger y últimamente Google Allo el cual integra Google Assistant, aunque esta última aún se espera que se abra a los desarrolladores en diciembre.

Además de productos destinados para el hogar que ofrecen una interfaz puramente conversacional a través de voz tales como Amazon Echo y Google Home (próximamente).

Queda claro que esta será la inevitable tendencia y más productos verán la luz, pero aún hay cuestiones por resolver.

## ¿Estamos preparados?

![¿Preparados?](/images/chatbot-robot.jpeg)

Volviendo a las preguntas iniciales, _¿No deberían muchos de los servicios que usamos diariamente adaptarse a ese medio?_ Sí. _¿No debería ser el lenguaje nuestra principal interfaz?_ Por el momento quizás no del todo. La interrogante no es si estar o no estar, si no en cómo estar.

En los últimos años han habido grandes avances en machine learning y procesamiento de lenguaje natural, pero aún no son lo suficientemente potentes como para ser realmente una interfaz útil y no una frustración para el usuario. En la mayoría de los casos a los usuarios no les importa lo que tu chatbot tiene que decir, ellos simplemente quieren llevar a cabo una acción de la manera más rápida y sencilla posible.

Aunque aún no está del todo claro cual es la mejor forma, ya existen lo que podemos llamar **servicios cognitivos** por parte de [Microsoft](https://www.microsoft.com/cognitive-services), [Google](https://cloud.google.com/products/machine-learning/) e [IBM](https://www.ibm.com/watson/developercloud/services-catalog.html), por mencionar algunos, que ofrecen a los desarrolladores sus avances en las áreas antes mencionadas a través de APIs. También servicios más específicos para la creación de chatbots como [API.ai](https://api.ai/) y [Wit.ai](https://wit.ai/) (comprar tu dominio .ai debes).

Quizás no necesitemos necesariamente ser puramente conversacional (por el momento). Tanto Facebook Messenger como Google Allo tienen una plataforma de mensajería parecida en cuanto a los elementos con los cuales se pueden interactuar dentro de la conversación. Botones, respuestas rápidas y formas más estructuradas de mostrar información son elementos que ayudan a ello.

![1-800 flowers bot](/images/chatbot-flowers.png)

*1-800 flowers bot*

Pero la concepción en ambos es distinta, mientras Facebook Messenger es solo un medio para los chatbots Google Allo es el chatbot-asistente en si mismo.

Por otro lado los bots en Slack permiten ser llamados dentro de la misma conversación, lo cual resulta bastante útil.

Hay ideas que rescatar de todas las plataformas, lo importante al final del día como cualquier software es que funcione y cumpla su propósito, para lo cual no necesariamente tiene que hacer uso de inteligencia artificial.

Que tipos de servicios son los más adecuados en este tipo de medio, aún es algo por explorar, pero va siendo claro que tienen que ser acciones simples y concretas y no tanto de exploración, hay varios consejos a tomar para construir un chatbot pero al final del día aún nadie sabe como hacerlo de la manera correcta, por lo cual representa una oportunidad para innovar.

## ¿Hacia dónde iremos?

Los chatbots y la realidad virtual serán los temas principales en los próximos meses-años, por lo que es importante estar en ello desde ya.

¿Serán los chatbots las nuevas apps? Eso depende de como se plantee el modelo finalmente. Podríamos tener un asistente único que se convierta en la interfaz principal del dispositivo (no necesariamente smartphones), el cual se comunicaría con servicios de terceros enviándoles la information de manera estructurada, sin la necesidad de que el usuario haga instalación alguna. Google Assistant me parece el más cercano a seguir ese camino.

Si todos siguen ese modelo esa comunicación asistente-servicios podría convertirse en protocolo estándar para futuros sistemas parecidos, para no reinventar la rueda constantemente.

O podría ser que el sistema operativo sea tan solo la plataforma sobre la cual se comuniquen los chatbots pero cada uno de manera independiente y con una personalidad propia, tal cómo me parece Facebook Messenger.

![Animación de chatbots](/images/chatbot-animation.gif)

Además de poder ser llamados fácilmente desde cualquier conversación que estemos teniendo, de tal manera que siempre sean integrados al contexto actual, quizás ahí es donde esté su mayor potencial.

Yendo un poco mas allá, podría cada persona finalmente tener un chatbot asistente que nos represente en el mundo digital, es decir tanto de cara a nosotros mismos como también de cara a las demás personas (u otros bots), que aprenda de nosotros y sea nuestro medio a un Internet más personalizado, que nos pueda filtrar información realmente relevante, y en lugar de nosotros tener que aprender como interactuar con los servicios y/o dispositivos, estos aprendan como interactuar con nosotros.

Un bot como **asistente-perfil** al mismo tiempo, es algo precisamente en lo que he estado pensando y sobre lo cual probando ideas, decidí crear un bot que sea mi contraparte digital, que pueda responder algunas cosas sobre mi pero al mismo tiempo haga ciertas tareas cuando sea yo quien le hable, se encuentra en Facebook como **ArturoBot**.

En principio fue entrenado con todas mis conversaciones que me descargue de Facebook (por experimentar), pero ahora solo con preguntas más específicas, así que aún no responde demasiado.

![ArturoBot](/images/arturobot.gif)

*ArturoBot*

Nada aún está definido y hay muchas cosas por probar, así que manos a la obra. Si deseas compartir ideas sobre este tema no dudes en contactarme.

