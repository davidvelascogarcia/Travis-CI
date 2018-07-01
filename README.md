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

```bash

language: cpp
os: linux
dist: trusty
sudo: enabled

compiler: 
 #  - gcc
   - clang


before_install:
  - sudo apt-get -qq update

  #-- Configure Git (needed by YCM)
  - if [ ! `git config --get user.email` ]; then `git config --global user.email 'user@example.com'`; fi
  - if [ ! `git config --get user.name` ]; then `git config --global user.name 'Travis CI'`; fi

install:


before_script:
  - mkdir build
  - cd build
  - cmake ..

script:
  - make

after_success:
  - sudo make install
  - Prueba_Travis_CI
  - sudo make uninstall

notifications:
  email: true

```

## Enlaces de interés

[Travis CI](https://travis-ci.org/)
