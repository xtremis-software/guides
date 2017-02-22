# GIT

## Workflow

* La rama de entorno de desarrollo es `master`. Sin embargo, no es un "work in progress". El desarrollo real se realiza en "feature branchs", cuyos cambios se pasan a master una vez finalizada la funcionalidad.

* La rama `staging` contiene la versión que actualmente puede consultar el cliente en su entorno de pruebas.

* La rama `production` contiene la versión que actualmente está en producción.

* Para casos en que es necesario un "hotfix", realizar el cambio directamente en la rama `staging` o `production` (según sea el caso) e incorporar inmediatamente los cambios a `master`. Las ramas `staging` y `production` no se utilizan para nada más que esto.

## Mensajes

* En inglés.
* Utilizar mensajes descriptivos que expliquen el porqué del cambio. Si es necesario, explicar posibles consecuencias del cambio y el cómo se ha implementado sin ser necesario entrar en detalles.
* Utilizar formato 50/72: 50 caracteres como máximo para la primera línea, una línea en blanco a continuación y 72 caracteres como máximo para las siguientes.

## Referenciación de issues

* Referenciar la issue a la que el commit hace referencia. Por ejemplo: `#122`.
* Aprovechar las funcionalidades de github para [cerrar la issue directamente desde el mensaje](https://help.github.com/articles/closing-issues-via-commit-messages/). Por ejemplo: `Closes #122`
  
  Esto se puede [automatizar mediante hooks de git](http://waiting-for-dev.github.io/blog/2014/07/19/append-issue-number-to-commit-message-automatically-with-git-hooks/), siguiendo cierta convención a la hora de nombrar la feature branch.
