# NodeRed-Epever-Rpi
**Dashboard de NodeRed para instalar en raspberry pi**

Este dashboard soluciona el problema de monitoreo de los sistemas solares aislados de la organización, estos constan de: 
  - Paneles solares de 150w a 12v
  - Baterías de ciclado profundo de 12v
  - Controladores de Carga PWM Epever LandStar y controladores de carga MPPT Epever XTRA
  - Raspberry pi 3
  - Adaptador USB a RS-485
La lectura del estado del sitio se realizará mediante consultas a los controladores de carga, para saber

**Instalación del Raspberry Pi**
1. Como primer paso necesitaremos descargar la aplicación llamada imager, esta es la encargada de descargar la imagen de raspbian que requiramos para posteriormente ser instalada la microSD.
   También es posible seleccionar opciones extras (ctrl+shift+x), como son activar el ssh, asignar un hostname, configurar el wifi y seleccionar el país del wifi, también podemos elegir la zona horaria y el teclado.
  - > sudo apt install rpi-imager
2. Conectamos la rpi a la energía y a la red para empezar a configurarla y nos conectamos a ella por ssh desde nuestro equipo. El hostname es el que asignamos en el punto anterior.
  - > ssh pi@hostname.local
3. Inciamos la preparación de nuestro equipo.Para esto ejecutamos la configuración del rpi, para expandir la memoria
  - > sudo raspi-config
4. Actualizamos el equipo para estar al día
  - > sudo apt update
  - > sudo apt upgrade
5. Con esto terminamos la instalación principal de la rpi y procederemos a la instalación  

**Instación de Nodered**
1. Debemos instalar nodered
  - > sudo apt install nodered
2. Activamos el nodered
  - > sudo systemctl enable nodered.service
3. Reiniciamos nodered
  - > sudo systemctl restart nodered.service
4. Entramos a la pagina principal de nodered desde la dirección https://direccionip:1880 
5. Accedemos a la opción de menús
![This is an image](https://github.com/inFERk/NodeRed-Epever-Rpi/blob/main/images/menu-importar-nodered.png)
6. En el menu anterior seleccionamos manage palette y vamos a instalar las siguientes nodos desde la opcion install.
  - > node-red-dashboard
  - > node-red-contrib-modbus
  - > node-red-contrib-influxdb
  - > node-red-contrib-moment
7. Importamos el archivo json con el desarrollo del dashboard. Esto lo realizamos entrando en el menú del punto 5 y seleccionamos import, para anexar el dashboard ya cargado.
![This is an image](https://github.com/inFERk/NodeRed-Epever-Rpi/blob/main/images/importar-json.png)
9. Finalizaremos nuestro darshboar y se verá de la siguiente manera.
![This is an image](https://github.com/inFERk/NodeRed-Epever-Rpi/blob/main/images/pantalla-nodered.png)
