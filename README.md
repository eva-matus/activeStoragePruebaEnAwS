# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version: 
  -v para Ruby 2.5.4
  -v para Rails 5.2.4, -v mas estables

* Gemas a utilizar:


  Para el correcto procesamiento de las imagenes y modificacion de las mismas, utilizare las siguientes:

* # Use ActiveStorage variant


* gem 'mini_magick', '~> 4.8'
* gem 'rmagick'
* gem 'image_processing'

* Configuration:


  Para la configuracion, practicamente necesitare utilizar activestorage, para el buen manejo en la nube, en este
  caso el servicio de AWS(ademas te ofrece un año gratis).

* Database creation:


 La bd creada con postgresql una bd no pequeña, pero para el buen uso en caso de subir a Heroku, necesariamente necesitas que estas
 se lleven 'bien', digo; para que sean compatibles.

* Services: AWS


 La configuracion de las variables de entorno en esta parte antes de subir cualquier aplicacion a la nube, juegan un papel super
 importante:
  ej: 
  amazon:
  service: S3                                            (este es el tipo de servicio que vas a utilizar en la nube)
  access_key_id: <%= ENV['AWS_ACCESS_KEY_ID'] %>         (este tipo de llaves 'variables de entorno', son muy utiles)
  secret_access_key: <%= ENV['AWS_SECRET_ACCESS_KEY'] %> (las variables de entorno nos puede hacer ahorrar mucho dinero)
  region: us-east-1                                      (nombre y region en la que creaste tu bucket)
  bucket: nombreDeTuBucket                               (en minuscula)

* Para la corecta applicacion de los token de seguridad, configurar lo siguiente:



class ApplicationController < ActionController::Base
    skip_before_action :verify_authenticity_token
end
