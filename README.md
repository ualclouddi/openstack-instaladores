# Scripts de post-instalación en instancias OpenStack

Al crear una instancia en OpenStack-DI es posible aprovisionarla o configurarla durante su proceso de creación. De esta forma, nuestras instancias ya tendrán instalados y configurados los paquetes necesarios.
 
Aqui podrás encontrar scripts para incluir en la pestaña de **Configuración** en la interfaz Horizon o para incluirlos en la línea de comandos si usas el CLI de OpenStack.

## Aviso

> Los scripts disponibles sólo son válidos para Ubuntu. No obstante, los scripts son fáciles de adaptar a otras distribuciones de Linux.


![](configuracion.png)

En la figura se ilustra la creación de una instancia Ubuntu con la el script siguiente para la instalación de Docker. También es posible cargar el script desde un archivo.

```
#!/bin/bash

echo "Instalando Docker"

apt-get update
apt-get install -y \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -
apt-key fingerprint 0EBFCD88
add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
apt-get update
apt-get install -y docker-ce
groupadd docker
usermod -aG docker ubuntu
systemctl enable docker

echo "Instalando Docker Compose"
curl -L "https://github.com/docker/compose/releases/download/1.23.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose

exit 0
```

## Scripts disponibles

* [Actualización de paquetes](https://gist.github.com/ualmtorres/0d77c4f197cbef860558d38b177a42bc)
* [Acceso a instancias con usuario y contraseña](https://gist.github.com/ualmtorres/c3e7123d3e414e9e54ad4d3ee1051429)
* [Ansible](https://gist.github.com/ualmtorres/04f3044594663006a71da3bad848e676)
* [Configuración de varias claves SSH públicas](https://gist.github.com/ualmtorres/2b7bb36502a90bea6d0c573d2356a167)
* [Docker CE y Docker Compose](https://gist.github.com/ualmtorres/dec19ebed2981459f8e5677979eb04c3)
* [Instalación sencilla de paquetes](https://gist.github.com/ualmtorres/67c4f1c19faed26f30da899b93318acc)
* [Python 2.7](https://gist.github.com/ualmtorres/572bc7cdc54c8ab51471e30375e06c3b)
* [PHP en Ubuntu](https://gist.github.com/ualmtorres/0575fc46623867c95894482f864d687e)
* [MySQL en Ubuntu](https://gist.github.com/ualmtorres/8a148ed5e5bcd469bfea37ac07c09824)
* Más scripts disponibles en [cloud-init](https://cloudinit.readthedocs.io/en/latest/topics/examples.html)
