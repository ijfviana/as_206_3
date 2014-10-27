## Mensajes inmediatos (I)

<div class="alert alert-info">
Los comandos [`shutdown`](http://linux.die.net/man/8/shutdown) y [`wall`](http://linux.die.net/man/1/wall) permiten mandar mensajes instantáneos
</div>

<a class="fancybox" href="img/mensajes_online.png" data-fancybox-group="gallery" title="mensajes instantáneos">
<img height="550px" src="img/mensajes_online.png" alt="mensajes instantáneos">
</a>

note:
* Two tools that enable you to send messages to users in real time, rather than when they log into the computer, are:
 * Shutdown Alerts One particularly important type of user communication is the shutdown alert. You can pass a message to all text-mode users when you shut down the system via the shutdown command.
 * Writing to All Terminals The Unix and Linux wall command writes a message to all active terminals—that is, to all text-mode logins. The wall command may be invoked by any user, but its exact usage differs from one distribution to others.



## Mensajes inmediatos (II)
### Ejemplos
```bash
ijfviana@vagalume:/usr/src/vboxhost-4.2.18$ sudo shutdown -h +10 “System going down for maintenance“

Emitiendo mensajes desde ijfviana@vagalume
  (/dev/pts/2) en 18:57 ...

The system is going down for halt in 10 minutes!
“System going down for maintenance“
```

```bash
ijfviana@vagalume:/usr/src/vboxhost-4.2.18$ echo  “System going down for maintenance“ | wall

Mensaje de difusión general (broadcast) de ijfviana@vagalume
        (/dev/pts/2) at 18:55 ...

System going down for maintenance
```

note:
* shutdown -h +10 “System going down for maintenance“ displays the message "System going down for maintenance" to all users with increasing frequency until the system shuts down.
* echo  “System going down for maintenance“ | wall display the message “System going down for maintenance“ to all users



## Mensajes inmediatos (III)

<div class="alert alert-info">
El comando [`mesg`](http://linux.about.com/library/cmd/blcmdl1_mesg.htm) controla el acceso de escritura al terminal
</div>

<a class="fancybox" href="img/wall_mesg.png" data-fancybox-group="gallery" title="Comando msg">
<img height="550px" src="img/wall_mesg.redimensionado640x480.png" alt="Comando msg">
</a>

note:
* Users can block wall messages by using the mesg command,
 * in mesg n to block messages or
 * mesg y to re-enable messages.
