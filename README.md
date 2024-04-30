# Homelab de Blinkito

[![Bienvenid@s](https://imgur.com/a/8K9rEZi)](https://github.com/blinkitogaming)

**¡Bienvenid@!**

**Soy Blinkito, aunque mi nombre real es Víctor. Soy un apasionado de la tecnología, sobretodo IoT y redes y me gustaría compartir contigo esta gran afición.**

En este repositorio encontrarás toda la documentación y archivos de configuración que uso en mi **Homelab**. También encontrarás notas, setups, configuración para la infraestructura, aplicaciones, redes y más.

>Te en cuenta que la configuración de aplicaciones y servicios puede cambiar con el tiempo. Aunque hago todo lo que puedo para mantener la documentación lo más actualizada posible puede que no siempre sea así.

## Contribución
Dado que es mi documentación personal, no acepto contribuciones, pero siempre puedes crear un fork del repositorio y usarlo como tu propia documentación.

## Otros recursos
- [Starship-and-ZSH-shell---Linux](https://github.com/blinkitogaming/Starship-and-ZSH-shell---Linux) - Mi configuración para ZSH
- [cheat-sheets](https://github.com/blinkitogaming/cheat-sheets) - Trucos recurrentes para varios SO y/o aplicaciones.
- [WOL-bash-script](https://github.com/blinkitogaming/WOL-bash-script) - Un simple script para monitorear servidores o equipos en LAN.
- [Backup-plan](https://github.com/blinkitogaming/backup-plan) - Mi configuración de sistema de copias de seguridad

### ¿Cómo llegué aquí?
Para empezar, digamos que no soy ningún experto, todo lo que hago aquí es fruto de mi propia experiencia y de aprender a base de fallos y errores. Aunque creo que cuando cometes un error es cuando mejor aprendes.

Tengo un Homelab muy humilde. Mi servidor principal es un equipo de gama doméstica montado por mí mismo en el que instalé **unRaid**.

Ya llevaba tiempo trabajando con este SO basado en Linux. Sin embargo, mis comienzos fueron, como para muchos otros, una simple **Raspberry 3B+** corriendo **OpenMediaVault**. Más que nada por la facilidad de poder hacer la configuración del sistema desde una interfaz gráfica porque al principio a todos nos asusta bastante la Terminal.

Con el tiempo quería pasar a algo con más potencia para poder tener más servicios corriendo. Fue así como allá por el año 2018 llegué a conocer **unRaid**, que por aquel entonces cosechaba bastantes adeptos.
Aproveché que jubilaba el ordenador que usaba para jugar y pasé a tener un servidor compuesto por:

- CPU: *Intel i5-6600K (4 núcleos/4 hilos)*
- RAM: *16GB DDR4-2133Mhz*
- ALMACENAMIENTO: *3x HDD (1 Seagate Barracuda de 1TB y 2 Seagate IronWolf de 4TB)*

Con el tiempo estaba muy contento con el sistema y empecé a ver cómo algunos creadores de contenido (*Linus Tech Tips* tiene la culpa...) montaban equipos con unRaid en el que corrían máquinas virtuales y hacía passthrough de la GPU para jugar en ella y me dije, **¡esto tengo que probarlo!**

Y así vendí la CPU y la placa base de mi servidor y compré lo necesario para montar un equipo lo suficientemente potente como para cacharrear con máquinas virtuales para jugar a la vez que seguía teniendo servidor. El nuevo equpo estaba compuesto por:

- CPU: *Ryzen 9 3900X (12 núcleos/24 hilos)*
- RAM: *16GB DDR4-3200Mhz*
- PLACA BASE: *Asus TUF x570-Plus*
- ALMACENAMIENTO: *3x HDD (1 Seagate Barracuda de 1TB y 2 Seagate IronWolf de 4TB)*
- ALMACENAMIENTO VM: *1x NVME Samsung 970 EVO Plus 500GB*
- GPU: *Nvidia GeForce GTX1050Ti 4GB*

Y acabé teniendo por un lado el servidor corriendo servicios como: *Plex, Tautulli, PiHole, Swag, Netdata, Deluge, Guacamole, CloudFlare, Vallheim Server, Homebridge, MariaDB, ShinobiPro (NVR), Overseerr, Jackett, Radarr, Sonarr, Unpackerr y páginas web en WordPress.*

Y por otro lado una máquina virtual con *Windows 10* con un *disco NVME y gráfica dedicados* a la que destinaba *6 núcleos/12 hilos* y *8GB de RAM* del servidor.

Así estuve casi **2 años** y excepto algún que otro error de configuración por mi parte que provocaba que la máquina virtual no arrancara todo fue genial.

Sin embargo, con el tiempo echaba de menos no tener que lidiar con pequeños inconvenientes como no poder conectar y desconectar periféricos (teclado, ratón, pendrives, webcam o discos externos) sin que la máquina virtual se bloqueara. Es cierto que intenté usar varias tarjetas PCIe USB, pero algunas no eran compatibles y otras no llegaban a funcionar del todo bien...

Es por eso que finalmente decidí volver a separar el PC para jugar/trabajar y el servidor en dos sistemas independientes.

Compré nuevos componentes y aproveché otros que tenía por casa y lo monté por separado. Y ahora es mi servidor principal en el que tengo:

- CPU: *Intel i3-10105 (4 núcleos/8 hilos)*
- RAM: *8GB DDR4-2133Mhz*
- PLACA BASE: *MSI B560M PRO-VDH*
- ALMACENAMIENTO: *12TB (4x Seagate IronWolf 4TB)*
- CACHÉ: *1x SSD SATA 480GB*

La configuración de almacenamiento está distribuida en 3 discos como almacenamiento útil (3x4TB) y uno como disco de paridad permitiendo así tolerar el fallo de un disco sin pérdida de datos.

Y un SSD de caché en el que están ubicados los archivos e imágenes de Docker, las bases de datos y el caché del sistema de archivos del array principal, al que se mueven cada noche los archivos liberando espacio en el SSD.

Por supuesto, todo con su correspondiente backup (puedes consultar más información en mi repositorio [Backup-plan](https://github.com/blinkitogaming/backup-plan)).

Además de este servidor también tengo un **Lenovo Thinkcentre M910q** con un i5-6600T y 16GB de RAM DDR4-2400Mhz en el que tengo instalado Proxmox y en el que actualmente tengo algunos servicios más corriendo separados del servidor principal. Con pensamiento de más adelante formar un clúster de 3 servidores Thinkcentre similares.
