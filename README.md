# Chuleta de Comandos de GIT

- https://git-scm.com/book/es/v1/Empezando-Configurando-Git-por-primera-vez
- Buenas prácticas mensajes commit: https://github.com/RomuloOliveira/commit-messages-guide/blob/master/README_es-AR.md
- Gitmoji: https://github.com/carloscuesta/gitmoji
- Dudas: http://programandonet.com/questions/75/git-push-requiere-nombre-de-usuario-y-contrasena
- Primera contribución: https://github.com/firstcontributions/first-contributions/blob/master/translations/README.es.md
- Autogenerador .gitignore: https://gitignore.io

## GIT FTP:

## Install

https://github.com/git-ftp/git-ftp/blob/master/INSTALL.md#macos
```
brew install git
brew install brotli
brew install git-ftp
```

### Setup

https://github.com/git-ftp/git-ftp
```
git config git-ftp.url "ftp://ftp.creacodigos.com:21"
git config git-ftp.user "ftpuser@creacodigos.com"
git config git-ftp.password "secr3t"
```

### Upload all files
```
git ftp init
```

### Or if the files are already there
```
git ftp catchup
```

### Work and deploy
```
echo "new content" >> index.txt
git commit index.txt -m "Add new content"
git ftp push
# 1 file to sync:
# [1 of 1] Buffered for upload 'index.txt'.
# Uploading ...
# Last deployment changed to ded01b27e5c785fb251150805308d3d0f8117387.
```

## Iniciar GIT

    git init
    
### Crear repositorio y vincular remoto

```
echo "# Comit inicial" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/creacodigos/nombreRepositorio.git
git push -u origin master
```

<strong>Añadir</strong> repositiorio remoto: (origin es el nombre por defecto)

    git remote add origin https://github.com/creacodigos/repositorio.git

<strong>Listar</strong> repositorio remoto:

    git remote -v

<strong>Modificar</strong> repositorio remoto

    git remote set-url origin https://github.com/creacodigos/nuevoRepositorio.git

Definiendo <strong>identidad</strong> global:

    git config --global user.name "Jorge"
    
    git config --global user.email "correo@correo.com"

    git config --global github.user usergithub
    
Definiendo <strong>identidad en repositorio específico</strong>:

    git config user.name "Jorge"
    
    git config user.email "correo@correo.com"

    git config github.user usergithub
    
    
## Credenciales
    
https://git-scm.com/book/es/v2/Herramientas-de-Git-Almacenamiento-de-credenciales

Forzar introducir <strong>usuario y contraseña</strong>:
Útil para cambiar de usuario

    git config --local credential.helper ""

## Monitorizar

<strong>Escuchando</strong> cambios de todo

    git add . 

<strong>Escuchando</strong> cambios de archivo

    git add README

<strong>Confirmar</strong> cambios y <strong>Commit</strong> inicial

    git commit –m 'versión inicial del proyecto'

## Clonar

<strong>Clonado</strong> repositorio en carpeta actual con directorio grit

    git clone git://github.com/creacodigos/grit.git

<strong>Clonando</strong> repositorio y rama específica

    git clone -b RAMA it://github.com/creacodigos/grit.git

<strong>Clonando</strong> repositorio en carpeta definida

    git clone git://github.com/creacodigos/grit.git carpeta


## Info

<strong>Comprobar</strong> estado de archivos

    git status

Ver lo que has <strong>modificado</strong> pero aún no has preparado

    git diff

<strong>Rehaciendo</strong> última confirmación

    git commit --amend

## Repositorios 

<strong>Mostrando</strong> repositorios remotos definidos:

    git remote

<strong>Recibiendo</strong> repositorio remoto y estados:

    git fetch [remote-name]

<strong>Enviando</strong> cambios a repositorio remoto

    git push origin master

<strong>Inspeccionando</strong> repositorio remoto

    git remote show origin

<strong>Eliminando y renombrando</strong> repositorios remotos

    git remote rename NOMBREVIEJO NOMBRENUEVO

<strong>Borrar</strong> repositorio remoto de la lista

    git remote rm origin

## Ramas

<strong>Creando</strong> nueva rama

    git branch testing


<strong>Cambiar</strong> a nueva rama

    git checkout testing


<strong>Creando</strong> rama y cambiando a la nueva rama

    git checkout -b 'nuevaRAMA'

<strong>Fusionar</strong> ramas a master con merge

    git checkout master

    git merge nuevaRAMA


<strong>Borrar</strong> rama local nueva tras ser fusionada

    git branch -d nuevaRAMA

<strong>Borrar</strong> rama local nueva SIN ser fusionada

    git branch -D nuevaRAMA


<strong>Borrar</strong> rama remota

    git push origin :rama


Mostrar <strong>listado</strong> de ramas del repositorio

    git branch


<strong>Publicando</strong> desde rama actual

    git push (remoto) (rama)

    git push origin master


<strong>Reorganizar</strong> rama sobre master sin comprobar previamente

    git rebase master rama

<strong>Deshacer</strong> cambios locales y commits y sincronizar con repositorio remoto
    
    git fetch origin
    
    git reset --hard origin/master

---

## Buenas prácticas mensajes commit

https://github.com/RomuloOliveira/commit-messages-guide/blob/master/README_es-AR.md

## gitmoji

https://github.com/carloscuesta/gitmoji

:art:
Mejora de la estructura / formato del código.

:zap:
Mejorando el desempeño.

:fire:
Eliminando código o archivos.

:bug:
Arreglando un error.

:ambulance:
Revisión crítica.

:sparkles:
Introduciendo nuevas funcionalidades.

:pencil:
Escribiendo documentos.

:rocket:
Desplegando cosas.

:lipstick:
Actualización de la UI y archivos de estilo.

:tada:
Compromiso inicial.

:white_check_mark:
Actualización de pruebas.

:lock:
Solucionar problemas de seguridad.

:apple:
Arreglando algo en macOS.

:penguin:
Arreglando algo en Linux.

:checkered_flag:
Arreglando algo en Windows.

:robot:
Arreglando algo en Android.

:green_apple:
Arreglando algo en iOS.

:bookmark:
Liberación / etiquetas de versión.

:rotating_light:
Eliminando las advertencias de la impresora.

:construction:
Trabajo en progreso.

:green_heart:
Arreglando CI Build.

:arrow_down:
Dependencias de degradación.

:arrow_up:
Actualización de dependencias.

:pushpin:
Fijación de dependencias a versiones específicas.

:construction_worker:
Añadiendo el sistema de compilación de CI.

:chart_with_upwards_trend:
Añadiendo analíticas o código de seguimiento.

:recycle:
Código de refactorización.

:whale:
Trabajar sobre Docker.

:heavy_plus_sign:
Añadiendo una dependencia.

:heavy_minus_sign:
Eliminando una dependencia.

:wrench:
Cambio de archivos de configuración.

:globe_with_meridians:
Internacionalización y localización.

:pencil2:
La corrección de errores tipográficos.

:poop:
Escribiendo código mal que necesita ser mejorado.

:rewind:
Deshaciendo cambios.

:twisted_rightwards_arrows:
Fusionando ramas.

:package:
Actualización de archivos o paquetes compilados.

:alien:
Actualización del código debido a cambios externos en la API.

:truck:
Mover o renombrar archivos.

:page_facing_up:
Agregando o actualizando licencia.

:boom:
Introduciendo los cambios de última hora.

:bento:
Adición o actualización de activos.

:ok_hand:
Actualización del código debido a cambios en la revisión del código.

:wheelchair:
Mejora de la accesibilidad.

:bulb:
Documentando el código fuente.

:beers:
Escribiendo el código borracho.

:speech_balloon:
Actualización de textos y literales.

:card_file_box:
Realización de cambios relacionados con la base de datos.

:loud_sound:
Añadiendo logs.

:mute:
La eliminación de registros.

:busts_in_silhouette:
Añadiendo contribuyente (s).

:children_crossing:
Mejora de la experiencia de usuario / usabilidad.

:building_construction:
Haciendo cambios arquitectónicos.

:iphone:
Trabajando en diseño responsivo.

:clown_face:
Cosas burlonas.

:egg:
Añadiendo un huevo de pascua.

:see_no_evil:
Agregar o actualizar un archivo .gitignore

:camera_flash:
Añadiendo o actualizando instantáneas.

:alembic:
Experimentando cosas nuevas.

:mag:
Mejora SEO

:wheel_of_dharma:
Trabajar sobre Kubernetes

:label:
Agregando o actualizando tipos (Flow, TypeScript)
