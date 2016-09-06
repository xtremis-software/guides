# GIT

## Workflow

* La rama de entorno de desarrollo es `master`. Sin embargo, no es un "work in progress". El desarrollo real se realiza en "feature branchs", cuyos cambios se pasan a master una vez finalizada la funcionalidad.

* La rama `staging` contiene la versión que actualmente puede consultar el cliente en su entorno de pruebas.

* La rama `production` contiene la versión que actualmente está en producción.

* Para casos en que es necesario un "hotfix", realizar el cambio directamente en la rama `staging` o `production` (según sea el caso) e incorporar inmediatamente los cambios a `master`

## Mensajes

* En inglés.
* Utilizar mensajes descriptivos que expliquen el porqué del cambio. Si es necesario, explicar posibles consecuencias del cambio y el cómo se ha implementado sin ser necesario entrar en detalles.
* Utilizar formato 50/72: 50 caracteres como máximo para la primera línea, una línea en blanco a continuación y 72 caracteres como máximo para las siguientes.
