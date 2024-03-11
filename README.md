# Creación de blogs con Jekyll y GitHub Pages

**Jekyll** es un generador de sitios web estáticos que nos permite crear de forma sencilla blogs, sitios webs personales o webs para proyectos. Los sitios webs generados con **Jekyll** no usan una base de datos, el contenido del sitio web está escrito en archivos de texto plano en formato **Markdown** (o **Textile**) y plantillas **Liquid**.

**Jekyll** es el motor de **GitHub Pages**, un servicio que ofrece GitHub a sus usuarios para que puedan publicar sitios webs estáticos alojados en los repositorios que tienen en **GitHub**.

De este modo, mediante **GitHub Pages** vamos a poder realizar la publicación de nuestro sitio web estático directamente en nuestro repositorio, poniendole como nombre a este, el que tenemos puesto de usuario en nuestro **GitHub**, seguido de ".github.io". 
En este caso el repositorio será puesto como público. Para ello estaremos utilizando tambien el **Codespace** del repositorio el cual es un servicio que permite a los desarrolladores crear y gestionar entornos de desarrollo en la nube para sus proyectos directamente desde el navegador web o desde **Visual Studio Code**. 

# 1 Creación de un contenedor Docker con Jekyll

# 1.1 jekyll new

Este comando nos permite crear la estructura de directorios y los archivos necesarios de un nuevo proyecto **Jekyll**.

```
docker run -it --rm -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll new blog
```

# 1.2 jekyll build

Aqui nuevamente contamos con nuestro **WorkFlow** para automatizar las tareas, pero igualmente indico cual sería el comando para realizar el **build**, el cual permite generar un sitio **HTML estático** a partir del contenido del proyecto **Jekyll**.

```
docker run -it --rm -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll build
```
# Estructura básica del sitio

Dentro del archivo de configuración **config.yml**, donde se Jekyll nos da la bienvenida, este es un archivo de configuración destinado para ajustes que afectan a todo tu blog, valores que se espera que configures una vez y rara vez edites después de eso. 
En mi caso establezco valores como el título del sitio, email...

```
# Welcome to Jekyll!
#
# This config file is meant for settings that affect your whole blog, values
# which you are expected to set up once and rarely edit after that. If you find
# yourself editing this file very often, consider using Jekyll's data files
# feature for the data you need to update frequently.
#
# For technical reasons, this file is *NOT* reloaded automatically when you use
# 'bundle exec jekyll serve'. If you change this file, please restart the server process.
#
# If you need help with YAML syntax, here are some quick references for you: 
# https://learn-the-web.algonquindesign.ca/topics/markdown-yaml-cheat-sheet/#yaml
# https://learnxinyminutes.com/docs/yaml/
#
# Site settings
# These are used to personalize your new site. If you look in the HTML files,
# you will see them accessed via {{ site.title }}, {{ site.email }}, and so on.
# You can create any custom variable you would like, and they will be accessible
# in the templates via {{ site.myvariable }}.

title: Título de mi blog, Samuel_IAW
email: samuel@example.com
description: >- # this means to ignore newlines until "baseurl:"
 Blog para el módulo de IAW
baseurl: "" # the subpath of your site, e.g. /blog
url: "" # the base hostname & protocol for your site, e.g. http://example.com
twitter_username: jekyllrb
github_username:  jekyll

# Build settings
theme: minima
plugins:
  - jekyll-feed

# Exclude from processing.
# The following items will not be processed, by default.
# Any item listed under the `exclude:` key here will be automatically added to
# the internal "default list".
#
# Excluded items can be processed by explicitly listing the directories or
# their entries' file path in the `include:` list.
#
# exclude:
#   - .sass-cache/
#   - .jekyll-cache/
#   - gemfiles/
#   - Gemfile
#   - Gemfile.lock
#   - node_modules/
#   - vendor/bundle/
#   - vendor/cache/
#   - vendor/gems/
#   - vendor/ruby/
```
