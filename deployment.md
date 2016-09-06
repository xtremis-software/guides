# Deployment

Intentamos difuminar las responsabilidades de desarrollo y puesta en marcha entre todos los desarrolladores.

* Normalmente, como servidor utilizamos [heroku](https://heroku.com), precisamente debido a que su facilidad promociona la colaboración de todo el equipo.
* Subir al entorno `development` mediante el sistema de Continuos Delivery. Para tener más agilidad en el caso que otro desarrollador esté esperando nuestro trabajo, también se permite subir directamente al servidor.
* Subir a `staging` y `production` mediante el sistema de [pipelines de heroku](https://devcenter.heroku.com/articles/pipelines) (`development --> staging --> production`), siempre y cuando el build de `development` haya tenido éxito. Nunca subir a los servidores de `staging` y `production` directamente, excepto en caso de mucha urgencia.
