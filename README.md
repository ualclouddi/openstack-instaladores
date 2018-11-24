# Scripts de post-intsalación en instancias OpenStack

Al crear una instancia en OpenStack-DI es posible aprovisionarla o configurarla durante su proceso de creación. De esta forma, nuestras instancias ya tendrán instalados y configurados los paquetes necesarios.
 
Aqui podrás encontrar scripts para incluir en la pestaña de **Configuración** en la interfaz Horizon o para incluirlos en la línea de comandos si usas el CLI de OpenStack.

## Aviso

> Los scripts disponibles sólo son válidos para Ubuntu. No obstante, los scripts son fáciles de adaptar a otras distribuciones de Linux.


![](configuracion.png)

En la figura se ilustra la creación de una instancia Ubuntu con la el script siguiente para la instalación de Docker. También es posible cargar el script desde un archivo.

<script src="https://gist.github.com/ualmtorres/dec19ebed2981459f8e5677979eb04c3.js"></script>

## Scripts disponibles

* [Docker CE y Docker Compose](scripts/docker.sh)