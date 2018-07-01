# Travis CI: Continuous Integration
[![Build Status](https://travis-ci.org/davidvelascogarcia/Travis-CI.svg?branch=master)](https://travis-ci.org/davidvelascogarcia/Travis-CI)

- [Introducción](#introducción)
- [Sintaxis](#sintaxis)
	- [Ejemplo de sintaxis](#ejemplo-de-sintaxis)
- [Enlaces de interés](#enlaces-de-interés)

## Introducción

Repositorio dedicado a pruebas de integración continua y control con **Travis CI**.

## Sintaxis

Para más información consulte: [Travis CI Sitio Web](https://travis-ci.org/).

### Ejemplo de sintaxis

Ejemplo fichero `.travis.yml`:

```yml

# Integración continua Travis CI

# Lenguaje de programación

language: cpp

# Sistema operativo destino a probar

os: linux

# Distribución del sistema operativo

dist: trusty

# Requerimiento de permisos en Linux

sudo: enabled

# Compiladores a emplear

compiler: 
#  - gcc
   - clang

# Tareas a realizar antes de instalacción

before_install:

# Actualizar

  - sudo apt-get -qq update

# Configurar Git si no lo está

  - if [ ! `git config --get user.email` ]; then `git config --global user.email 'user@example.com'`; fi
  - if [ ! `git config --get user.name` ]; then `git config --global user.name 'Travis CI'`; fi

# En caso de requerir instalar algo para la prueba

install:


# Tareas a ejecutar antes de nuestra prueba

before_script:
  - mkdir build
  - cd build
  - cmake ..

# Compilamos

script:
  - make

# En caso de compilación exitosa

after_success:
  - sudo make install
  - Prueba_Travis_CI
  - sudo make uninstall

# Notificaciones por correo

notifications:
  email: true

```

## Enlaces de interés

[Travis CI](https://travis-ci.org/)
