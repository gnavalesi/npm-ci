# NPM + GitHub

* `npm install`
* `npm install -g gulp-cli`

## Gulp

Gulp es un build system para javascript que prioriza código por sobre configuración. Existen centenares de plugins destinados a distintas tareas como mover archivos, ejecutar tests, calcular la covertura de los tests, etc...

En _Gulpfile.js_ hay 3 tareas configuradas, dedicadas a ejecutar los tests, calcular la covertura y enviar los datos a _Coveralls_ (simil Sonar).

## Servicios de GitHub

### Travis ([https://travis-ci.org/](https://travis-ci.org/))

[![Build Status](https://travis-ci.org/gnavalesi/npm-ci.svg?branch=master)](https://travis-ci.org/gnavalesi/npm-ci)

Para configurar _Travis_ hay que habilitar el servicio desde Github y crear el archivo _.travis.yml_ en el directorio raiz de nuestro repositorio. En el caso de este proyecto, el contenido es el siguiente:

```yaml
language: node_js
node_js: "4.4"

before_script:
  - npm install
  - npm install -g gulp

script: gulp ci
```

Cada vez que se haga push, por cada commit _Travis_ instala el proyecto y ejecuta `gulp ci`

### Coveralls ([https://coveralls.io](https://coveralls.io))

[![Coverage Status](https://coveralls.io/repos/github/gnavalesi/npm-ci/badge.svg?branch=master)](https://coveralls.io/github/gnavalesi/npm-ci?branch=master)

Ya tenemos configurada la tarea de _Gulp_ que envía los datos de covertura a _Coveralls_ para que los analice. Lo único que tenemos que hacer es ingresar al sitio web y habilitar el análisis para el repositorio.

### Code Climate ([https://codeclimate.com](https://codeclimate.com))

[![Code Climate](https://codeclimate.com/github/gnavalesi/npm-ci/badges/gpa.svg)](https://codeclimate.com/github/gnavalesi/npm-ci)

_Code Climate_ permite detectar posibles errores en nuestro código. También permite el análisis de datos de covertura.

### VersionEye ([https://www.versioneye.com](https://www.versioneye.com))

_Version Eye_ analiza las dependencias de nuestro proyecto, detectando nuevas versiones y problemas de seguridad.
