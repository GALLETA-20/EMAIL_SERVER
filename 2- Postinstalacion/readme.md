# Post instalación del sistema operativo Armbian
## Primer arranque
Cuando el sistema operativo arranca por primera vez, el sistema pedirá información:
  - Contraseña de usuario `root`.
  - Creación de usuario:
    - Nombre de usuario.
    - Contraseña de usuario. 
  - Zona Horario.
  - Idioma y distribución del teclado.
  - Configuración de red.

> `Nota: La configuración horaria es importante para la actualización del sistema.`
> 
> `Ojo: Algunas opciones se seleccionan ingresando el número correspondiente de la lista mostrada.`

## Actualización del sistema
Antes de actualizar el sistema hay que comprobar la fecha y hora registradas.
`# timedatectl`
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
