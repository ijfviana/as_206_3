## Mensajes de login (I)

<a class="fancybox" href="img/login_message.png" data-fancybox-group="gallery" title="Mensajes login">
<img height="550px" src="img/login_message.redimensionado640x480.png" alt="Mensajes login">
</a>

note:
* When users log in via a text-mode login prompt, either at the console or remotely, the computer displays various
messages. The login: prompt itself is one such message, but you can manipulate some others:
 * Local Login Messages The `/etc/issue` file holds a message that’s displayed above the login: prompt at a textmode console.
 * Network Login Messages The /etc/issue.net file is similar to /etc/issue, but it holds information that’s displayed by the Telnet server just before it presents the login.
 * Message of the Day The message of the day (MOTD) is a message that’s stored in /etc/motd.
 * Fortunes Some system administrators like to spice up the login experience with a pithy saying.



## Mensajes de login (II)
### Ejemplos

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



## Mensajes de login (III)
### Variables en /etc/issue*

<div class="table-responsive">
<table class="table table-hover table-bordered">
<thead>
<tr>
<th>Variable</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr>
<td>\n</td>
<td>Nombre del ordenador</td>
</tr>
<tr>
<td>\r</td>
<td>Versión del núcleo</td>
</tr>
<tr>
<td>\s</td>
<td>El nombre del Sistema Operativo</td>
</tr>
<tr>
<td>\m</td>
<td>La plataforma</td>
</tr>
<tr>
<td>\t</td>
<td>La fecha en la que se mostró el mensaje</td>
</tr>
</tbody>
</table>
</div>

note:
* The /etc/issue and /etc/issue.net files support variables that you can use to substitute information that might vary from one login to another or from one system to another
 * \n (the computer’s hostname),
 * \r (the kernel version number),
 * \s (the OS name—Linux),
 * \m(the platform, such as x86),
 * \t (the time when the message is printed).
* One problem with all of these communication methods is that they’re all geared toward text-mode users.
