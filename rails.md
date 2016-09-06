# Rails

## Stack

* Última versión estable de [Ruby](https://www.ruby-lang.org/en/downloads/)
* Última versión estable de [Rails](http://rubyonrails.org/)
* [Rspec](http://rspec.info/) para la suite de tests
* [Slim](http://slim-lang.com/) como lenguaje de template
* [Sass](http://sass-lang.com/) para las hojas de estilo
* [Coffeescript](http://coffeescript.org/) para javascript
* [Devise](https://github.com/plataformatec/devise) para la autenticación.
* [Pundit](https://github.com/elabs/pundit) para la autorización


## APIs

* En caso de API utilizar [jwt](https://jwt.io/) como capa encima de Devise para la autenticación.
* Utilizar las políticas CORS más restrictivas posibles con [rack-cors](https://github.com/cyu/rack-cors).

## Seguridad

* Seguir la [guía de seguridad de Ruby On Rails](http://guides.rubyonrails.org/security.html).
* Mantener actualizados a la última versión estable ruby y rails.
* A no ser que un gem indique lo contrario, utilizar [pesimistic semantic versioning](https://robots.thoughtbot.com/rubys-pessimistic-operator), mandando actualizar a la última versión que no rompe la API, a la hora de especificar las dependencias en el Gemfile. E.g.: `~> 2.1`
* Periódicamente, actualizar el Gemfile.
* Seguir las recomendaciones de seguridad de engines cómo bundler-audit o brakeman de overcommit (ver más abajo).
* Para aplicaciones bajo el dominio `herokuapp.com`, utilizar https con HSTS. Para otros casos, dependerá de lo acordado con el cliente.

## Consumo de memoria y performance

* Añadir dependencias a la aplicación con criterio. Cuanto más gems, más dependemos de código que puede cambiar y más cargamos la memoria de nuestra aplicación. Está claro que mejor utilizar gems de calidad que no implementar nuestra propia solución desde cero, pero hay que valorar los pros y contras.
* Añadir los gems al `environment` adecuado. Si un gem sólo se necesita en `development`, hay que ponerlo en ese `group` del Gemfile.
* Si un gem sólo es necesario para ejecutar tasks, se puede añadir en el Gemfile con la opción `require: false` y requerirlo en el Rakefile.
* Utilizar [rack-timeout](https://github.com/heroku/rack-timeout) con el valor más bajo posible.
* Instalar [newrelic](https://github.com/newrelic/rpm) para monitorizar.
* Ejecutar los procesos largos en background. Para casos sencillos, [sucker_punch](https://github.com/brandonhilkert/sucker_punch) es suficiente. Para cosas más intensivas, [sidekiq](https://github.com/mperham/sidekiq) o algún otro.
* Monitorizar periódicamente la aplicación. Podemos utilizar los siguientes recursos:
  * Logs de rails
  * New Relic
  * Logs de heroku
  * Para análisis más a fondo podemos utilizar [derailed_benchmarks](https://github.com/schneems/derailed_benchmarks)

## Calidad y estándares de código

Se trabajará con [overcommit](https://github.com/brigade/overcommit) para asegurar una calidad en el código y seguir unos estándares que permitan un mejor mantenimiento y crecimiento de la aplicación. Por defecto seguiremos la configuración inicial de cada engine, pero, por consenso, podemos adaptarlo.

El siguiente debe ser el `~/.overcommit.yml` en cuanto a ruby:

```
#
# Select version of overcommit and the other tools from Gemfile
#
gemfile: .overcommit_gems.rb

#
# Hooks that are run against every commit message after a user has written it.
#
CommitMsg:
  ALL:
    required: true

  HardTabs:
    enabled: true

  SingleLineSubject:
    enabled: true

#
# Hooks that are run after `git commit` is executed, before the commit message
# editor is displayed.
#
PreCommit:
  ALL:
    required: true

  BundleAudit:
    enabled: true

  BundleCheck:
    enabled: true

  LocalPathsInGemfile:
    enabled: true

  ExecutePermissions:
    enabled: true
    exclude:
      - bin/*

  Reek:
    enabled: true

  RuboCop:
    enabled: true

  TrailingWhitespace:
    enabled: true

  YamlSyntax:
    enabled: true

  RailsBestPractices:
    enabled: true

  RailsSchemaUpToDate:
    enabled: true

#
# Hooks that are run before pushing changes
#
PrePush:
  ALL:
    required: true

  RSpec:
    enabled: true

  Brakeman:
    enabled: true
```
