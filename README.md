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
