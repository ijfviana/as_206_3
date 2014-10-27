## Notificaciones a usuarios

* [Mensajes durante el login](#/7/1)
* [Mensajes inmediatos](#/7/4)

<aside class="notes">
Computers are used by people, and people can become annoyed if their computers shut down or otherwise
behave strangely at unexpected times. Thus, you should know how to communicate such issues with the users of a
computer. Sometimes this task can be accomplished by setting login messages, but other times you must send
messages to users in real time.
</aside>


### Configuración de mensajes de login (I)

<a class="fancybox" href="custom/contents/02_03/fig/login_message.png" data-fancybox-group="gallery" title="source issues">
<img height="550px" src="custom/contents/02_03/fig/login_message.png" alt="source issues">
</a>

<aside class="notes">
* When users log in via a text-mode login prompt, either at the console or remotely, the computer displays various
messages. The login: prompt itself is one such message, but you can manipulate some others:
 * Local Login Messages The /etc/issue file holds a message that’s displayed above the login: prompt at a textmode console.
 * Network Login Messages The /etc/issue.net file is similar to /etc/issue, but it holds information that’s displayed by the Telnet server just before it presents the login.
 * Message of the Day The message of the day (MOTD) is a message that’s stored in /etc/motd. 
 * Fortunes Some system administrators like to spice up the login experience with a pithy saying. 
</aside>


### Configuración de mensajes de login (II)
#### Ejemplos

```bash
ijfviana@linda:/tmp/as/tar-1.27/src$ cat /etc/motd 
Welcome to Ubuntu 12.04.3 LTS (GNU/Linux 3.8.0-31-generic x86_64)
 * Documentation:  https://help.ubuntu.com/
ijfviana@linda:/tmp/as/tar-1.27/src$ 
```

```bash
ijfviana@linda:/tmp/as/tar-1.27/src$ cat /etc/issue
Ubuntu 12.04.3 LTS \n \l
```
```bash
ijfviana@linda:/tmp/as/tar-1.27/src$ cat /etc/issue.net 
Ubuntu 12.04.3 LTS
```


### Configuración de mensajes de login (III)
#### Variables en /etc/issue*

| Variable | Descripción  |
|----------|--------------|
| \n       | Nombre del ordenador  
| \r       | Versión del núcleo 
| \s       | El nombre del Sitema Operativo
| \m       | La plataforma
| \t       | La fecha en la que se mostro el mensaje

<aside class="notes">
* The /etc/issue and /etc/issue.net files support variables that you can use to substitute information that might vary from one login to another or from one system to another 
 * \n (the computer’s hostname), 
 * \r (the kernel version number), 
 * \s (the OS name—Linux), 
 * \m(the platform, such as x86), 
 * \t (the time when the message is printed).
* One problem with all of these communication methods is that they’re all geared toward text-mode users. 
</aside>


### Mensajes inmediatos (I)

<a class="fancybox" href="custom/contents/02_03/fig/mensajes_online.png" data-fancybox-group="gallery" title="source issues">
<img height="550px" src="custom/contents/02_03/fig/mensajes_online.png" alt="source issues">
</a>

<aside class="notes">
* Two tools that enable you to send messages to users in real time, rather than when they log into the computer, are:
 * Shutdown Alerts One particularly important type of user communication is the shutdown alert. You can pass a message to all text-mode users when you shut down the system via the shutdown command.
 * Writing to All Terminals The Unix and Linux wall command writes a message to all active terminals—that is, to all text-mode logins. The wall command may be invoked by any user, but its exact usage differs from one distribution to others.
</aside>


### Mensajes inmediatos (II)
#### Ejemplos
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

<aside class="notes">
* shutdown -h +10 “System going down for maintenance“ displays the message "System going down for maintenance" to all users with increasing frequency until the system shuts down.
* echo  “System going down for maintenance“ | wall display the message “System going down for maintenance“ to all users 
</aside>


### Mensajes inmediatos (III)

<a class="fancybox" href="custom/contents/02_03/fig/wall_mesg.png" data-fancybox-group="gallery" title="source issues">
<img height="550px" src="custom/contents/02_03/fig/wall_mesg.png" alt="source issues">
</a>

<aside class="notes">
* Users can block wall messages by using the mesg command,
 * in mesg n to block messages or 
 * mesg y to re-enable messages.
</a>