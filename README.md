REDES2_2S2020_Proyecto2_201700944
Primero creare la página web a mostrar.

Se creo una instancia ec2 de AWS con Ubuntu 20 Se instalo el servidor Apache y se reemplazo la vista default que se encontraba en la ruta /var/www/html

Para copiar los archivos de la nueva página a la máquina virtual se utilizo el siguiente comando: scp -i miclavepracticanueva.pem -r html/ ubuntu@18.218.90.99:/var/www/ esto para poder sustiuir el index.html que tenia por defecto el servidor de apache

Se creo una instanci EC2 adicional para poder crear el LoadBalancer, en esta instancia, al igual que en la primera, se instalo el servidor de Apache
y se sustituyo la vista que tenia por defecto, por la página web diseñada, se utilizo el siguiente comando para copiar los archivos de la página a esta instancia:
scp -i clavepc2.pem -r html/ ubuntu@3.137.107.55:/var/www/

Se creo un LoadBalancer con las 2 instancias creadas anteriormente.

Se obtuvo un dominio gratuito en dominiosa1.com el cual fue http://www.redes2-201700944.mire.tv/ y se utilo el servicio de Route53 de AWS para enlazar el dominio
con el balanceador de carga creado con nuestras 2 instancias de EC2.
