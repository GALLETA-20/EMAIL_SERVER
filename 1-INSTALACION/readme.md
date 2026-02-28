# Instalación del Sistema Operativo Armbian
## ENLACES
- Armbian Debian 12 (Bookworm) minimal: https://www.armbian.com/orange-pi-zero-2w/.
- Balena Etcher: https://etcher.balena.io/
- Manual del fabricante Orange Pi: https://drive.google.com/drive/folders/1KIZMMDBlqf1rKmOEhGH7_7A-COAgYoGZ

## Requisitos
- Una tarjeta SD con las siguientes características:
  1. De clase 10 o mayor.
  2. Capacidad superior a 8 GB.
  3. Marca SanDisk
  (Si se usa otra sd que no cumpla con estas características, el sistema puede presentar fallos).
- Sistema operativo Debian 12 (Bookworm) versión mínimal.

  (La Orange Pi Zero 2W es un dispostivo pequeño y con ram limitada, se instala la versión minimal para tener un sistema limpio, libre de servicios que no necesitamos.
- Balena Etcher instalado

  (Nos sirve para bootear la tarjeta sd donde se instala el sistema operativo).

## Booteo
1. Descomprime el archivo "_Armbian_25.5.1_Orangepizero2w_bookworm_current_6.12.23_minimal.img_", automaticamente se crea una carpeta, dentro se encuentra un archivo con extensión .iso
<p align="center">
  <img src="capturas/EXTRAER.jpg" width="600">
</p>
<p align="center">
  <img src="capturas/ARCHIVO.jpg" width="600">
</p>

2. Ejecuta balena etcher como Administrador.
Si no se ejecuta como admnistrador el proceso de booteo fallará.

4. Selecciona el SO que está dentro de la carpeta extraida, luego la tarjeta sd y finalmente presionas Flash!.
<p align="center">
  <img src="capturas/BalenaEtcher.jpg" width="600">
</p>
   
