## Desplegar aplicación Java en Heroku

#### [Video Explicativo](https://www.youtube.com/watch?v=7p8jyidcNMs)

* Crear cuenta heroku
* [Crear nuevo proyecto](https://dashboard.heroku.com/new-app)
* Descargar e instalar GIT - Subir nuestro proyecto a GITHUB
* [Descargar e instalar Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)

  Para instalarlo en Mac utilizar la instrucción:
  
        brew tap heroku/brew && brew install heroku
      
* Crear un proyecto Java usando Maven
  la construcción del proyecto creará el archivo -1.war en la carpeta de destino
  Podemos crear el archivo war desde un jar:
  
        jar cvf servicioweb.war /ServicioWeb
  
* Inicializar Git en la carpeta del proyecto

          git init
          git add .
          git commit -am "Servicio Web Java - Primer commit"
    
* Implementar la aplicación en heroku utilizando heroku-cli
    
          heroku login
    
* Instalar heroku-cli-deploy plugin
    
          heroku plugins:install heroku-cli-deploy
    
* Deploy app on heroku
   
          heroku war:deploy target/<war_filename>.war --app <heroku-app-name>
  
* Lo ejecutamos

      heroku open --app java-trasslink



### [Creando una aplicación con Python y desplegando a Heroku](https://www.youtube.com/watch?v=PEcWR882goU)
   
Pasos: 
   
   - heroku login
   - creamos la carpeta /teatro/scraper
   - Creamos el ambiente virtual virtualenv dentro de la carpeta
   
       Para instalarlo:

          sudo easy_install pip
          pip3 install virtualenv (yo he usado pip3)


       Para crear el ambiente virtual:

          virtualenv venv

       Activarlo

          source venv/bin/activate
      

Una vez tenemos nuestro proyecto debemos declarar las dependencias con 2 archivos dentro de dicha la carpeta: 

    - requirements.txt
    - Procfile
    
**Para crear el requirements.tx**

    pip3 freeze > requirements.txt

**Procfile**

Debe contener la siguiente linea:

    web: python teatro-scraper
    
### Despliegue en Heroku utilizando GIT
- Creamos el archivo .gitignore dentro de la carpeta con el siguiente contenido:

    venv
    *.pyc

- git init
- git add .
- git commit -m "primer commit"
- heroku create (heroku create --app teatro-scraper)
- git push heroku master
- Elegimos la url donde se ha desplegado

