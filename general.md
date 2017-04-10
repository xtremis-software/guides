# General

Aspectos de tipo general sobre la cultura de la empresa y la dinámica de los proyectos.

## Metodología
- Tenemos claro que, para mejorar la calidad final de los proyectos y poder optar a mejores 
clientes, todo pasa por colaborar con gente comprometida, que tenga buena actitud y mejor nivel 
técnico. Se aplica principalmente a programadores, pero en realidad lo contemplamos para cualquier 
otro perfil.
- Vemos necesario intentar abandonar las prácticas actuales y mentalizarse para adoptar una forma de
 trabajo completamente asíncrona y remota. Esto implica, entre otras cosas, evitar las 
 interrupciones y utilizar las reuniones únicamente como último recurso, no como algo habitual.
- Excepto en proyectos con un único programador, nos guiaremos por la [metodología de ciclos de 
Basecamp](https://m.signalvnoise.com/how-we-set-up-our-work-cbce3d3d9cae#.kytlnn33n), que incluye 1 
semana de planificación (*pitch*) y 3 semanas de implementación.
- Usaremos únicamente 2 aplicaciones para gestionar los proyectos: **Basecamp** para comunicación 
con el cliente, valoraciones, y cualquier otra discusión transversal que no sea de tipo técnico, y 
**Github** para la construcción del proyecto en sí: requerimientos, *features*, *bugs*, 
preguntas, *milestones*, etc.
- Por ahora, aunque no haya tiempo material para llevarlas a cabo, seguimos proponiendo trabajar 
mediante *pull requests* y verificar las aplicaciones usando las [review apps de Heroku](https://devcenter.heroku.com/articles/github-integration-review-apps).

## Supervisión
- Realizaremos una supervisión general de los proyectos, cuya forma y enfoque aún están por 
concretar. Lo que sí destacamos es que es importante empezar a documentar todos y cada uno de los 
pasos que se realicen en un proyecto, para ayudar así a no perder el hilo y evitar las 
interrupciones o las reuniones constantes, que acaban siendo típicas y, aparentemente, 
imprescindibles cuando el proyecto no está bien organizado ni documentado.
- Para ayudar a realizar esta supervisión, utilizaremos una herramienta de análisis estático de 
código (seguramente **CodeClimate**) y otra de cobertura de código (como el propio CodeClimate o 
Coveralls) en aquellos proyectos en que consideremos que puede ser útil. Definiremos una serie de 
*hard rules* para evitar descalabros mayores en el código, pero en general no vemos eficiente 
plantear una política basada en la prohibición; es mejor hacer seguimiento y detectar cuanto antes 
problemas potenciales.

## Valoraciones
- Las valoraciones las deberían realizar, idealmente, las personas que vayan a implementar el 
proyecto, pero si no es posible, las realizaría alguna otra persona que forme parte 
del equipo de supervisión técnica en ese momento. 
- El tiempo de respuesta de las valoraciones lo determinamos en 1 semana como máximo para así no 
retrasar el contacto con el cliente.
- Las decisiones sobre tecnología (*framework*, lenguajes, librerías...) recaerán siempre sobre los
 técnicos del equipo de supervisión. De esta manera será más fácil unificar criterios y no tener 
 tanta diversidad, que al final acaba siendo un problema.

## Mantenimiento de aplicaciones
- Planteamos una propuesta de mantenimiento para aplicaciones finalizadas a los clientes que 
consistirá en una cuota fija de poco valor que incluirá la actualización de versiones menores 
(*point releases*) de las dependencias de la aplicación, así como parches de seguridad, si los 
hubiera. Los cambios mayores de versión se valorarán en función de cada caso.
- Las aplicaciones en desarrollo siempre procuraremos actualizarlas a la última versión disponible 
como parte del proceso de implementación.

## Otros
- En proyectos de cierta entidad, la empresa reservará una partida del presupuesto a posibles 
productos derivados, ya sea en forma de proyectos open-source, librerías o código común que 
podamos usar en otros proyectos, documentación extra, blog posts, etc. Es importante que los 
proyectos grandes sirvan para profundizar en el conocimiento de lo que hacemos, así como en la 
obtención de *assets* que puedan usarse en futuros proyectos o refuercen el impacto tecnológico de 
la empresa.
