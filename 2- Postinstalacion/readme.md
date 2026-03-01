# Post instalación del sistema operativo Armbian
## Primer arranque
Cuando el sistema operativo arranca por primera vez, el sistema pedirá información:
  - Contraseña de usuario `root`.
  - Creación de usuario:
    - Nombre de usuario.
    - Contraseña de usuario. 
  - Zona Horaria.
  - Idioma y distribución del teclado.
  - Configuración de red.
```
Nota: La configuración horaria es importante para la actualización del sistema.
Ojo: Algunas opciones se seleccionan ingresando el número correspondiente de la lista mostrada.
```
## Requisito antes de la actualización del sistema
Antes de actualizar el sistema hay que comprobar la fecha y hora registradas.  

Ejecutar el comando `timedatectl`.  

La respuesta del sistema será:  
```
root @ orangepizero2w: ~ # timedatectl
               Local time: dom 2026-03-01 00:49:02 -05
           Universal time: dom 2026-03-01 05:49:02 UTC
                 RTC time: dom 2026-03-01 05:48:31
                Time zone: America/Lima (-05, -0500)
System clock synchronized: yes
              NTP service: active
          RTC in local TZ: no
```
La información que muestra `Local time` debe ser igual a la hora y el día que registra su región.  
Si no lo es, ejecuta el siguiente comando:  
`# sudo date -s "$(TZ='America/Lima' date '+%Y-%m-%d %H:%M:%S')"`  
> Nota: Cambia 'America/Lima' por la región a la que perteneces.  
El camando `ls /usr/share/zoneinfo/` muestra las regiones bases.  
```
root @ orangepizero2w: ~ # ls /usr/share/zoneinfo/
Africa      CST6CDT  GB-Eire    iso3166.tab        MST         PST8PDT    WET
America     Cuba     GMT        Israel             MST7MDT     right      W-SU
Antarctica  EET      GMT+0      Jamaica            Navajo      ROC        zone1970.tab
Arctic      Egypt    GMT-0      Japan              NZ          ROK        zone.tab
Asia        Eire     GMT0       Kwajalein          NZ-CHAT     Singapore  Zulu
Atlantic    EST      Greenwich  leapseconds        Pacific     Turkey
Australia   EST5EDT  Hongkong   leap-seconds.list  Poland      tzdata.zi
Brazil      Etc      HST        Libya              Portugal    UCT
Canada      Europe   Iceland    localtime          posix       Universal
CET         Factory  Indian     MET                posixrules  US
Chile       GB       Iran       Mexico             PRC         UTC
```

Para ver las zonas dentro de una región base, ejecuta el comando `ls /usr/share/zoneinfo/[nombre de la región base]`.  
Ejemplo  `ls /usr/share/zoneinfo/America/`.
```
root @ orangepizero2w: ~ # ls /usr/share/zoneinfo/America/
Adak            Coral_Harbour  Havana         Moncton         Santa_Isabel
Anchorage       Cordoba        Hermosillo     Monterrey       Santarem
Anguilla        Costa_Rica     Indiana        Montevideo      Santiago
Antigua         Coyhaique      Indianapolis   Montreal        Santo_Domingo
Araguaina       Creston        Inuvik         Montserrat      Sao_Paulo
Argentina       Cuiaba         Iqaluit        Nassau          Scoresbysund
Aruba           Curacao        Jamaica        New_York        Shiprock
Asuncion        Danmarkshavn   Jujuy          Nipigon         Sitka
Atikokan        Dawson         Juneau         Nome            St_Barthelemy
Atka            Dawson_Creek   Kentucky       Noronha         St_Johns
Bahia           Denver         Knox_IN        North_Dakota    St_Kitts
Bahia_Banderas  Detroit        Kralendijk     Nuuk            St_Lucia
Barbados        Dominica       La_Paz         Ojinaga         St_Thomas
Belem           Edmonton       Lima           Panama          St_Vincent
Belize          Eirunepe       Los_Angeles    Pangnirtung     Swift_Current
Blanc-Sablon    El_Salvador    Louisville     Paramaribo      Tegucigalpa
Boa_Vista       Ensenada       Lower_Princes  Phoenix         Thule
Bogota          Fortaleza      Maceio         Port-au-Prince  Thunder_Bay
Boise           Fort_Nelson    Managua        Porto_Acre      Tijuana
Buenos_Aires    Fort_Wayne     Manaus         Port_of_Spain   Toronto
Cambridge_Bay   Glace_Bay      Marigot        Porto_Velho     Tortola
Campo_Grande    Godthab        Martinique     Puerto_Rico     Vancouver
Cancun          Goose_Bay      Matamoros      Punta_Arenas    Virgin
Caracas         Grand_Turk     Mazatlan       Rainy_River     Whitehorse
Catamarca       Grenada        Mendoza        Rankin_Inlet    Winnipeg
Cayenne         Guadeloupe     Menominee      Recife          Yakutat
Cayman          Guatemala      Merida         Regina          Yellowknife
Chicago         Guayaquil      Metlakatla     Resolute
Chihuahua       Guyana         Mexico_City    Rio_Branco
Ciudad_Juarez   Halifax        Miquelon       Rosario
```

## Actualización del sistema
1. Ejecutar:  
   `# sudo apt update`  
   Esperar a que el sistema termine de actualizar los repositorios.  
   
2. Ejecutar:  
   `# sudo apt upgrade -y`  
   Esperar a que el sistema termine de actualizar.  
 ```
 Advertencia!: No apagar la Orange Pi ni interrumpir el proceso de actualización.
 Si se interrumpe, pueden corromperse los archivos y el sistema queda inutilizable.
 ```
