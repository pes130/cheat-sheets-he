# Información sobre el Sistema Operativo
Mostrar nombre del PC, Versión del kernel, hostname y arquitectura
```bash
uname -a
```

Mostrar **información de la distribución**:
```bash
cat /etc/*-release
```


# Información hardware
Mostrar información sobre la **CPU**:
```bash
cat /proc/cpuinfo
```

Configuración de los **puntos de montaje**:
```bash
cat /etc/fstab
```

# Servicios locales a la escucha
Mostrar servicios escuchando en localhost:
```bash
ss -l
```


# Información sobre usuarios y grupos
Mostrar fichero de **usuarios**:
```bash
cat /etc/passwd
```

Mostrar fichero de **grupos**:
```bash
cat /etc/group
```

Mostrar **hashes de contraseñas** de usuarios (requiere privilegios):
```bash
cat /etc/shadow
```

Qué **usuario** soy:
```bash
whoami
```

Mi **uid** y mis **gid** (mi identificador de usuario y el de mis grupos):
```bash
id
``` 

Qué **usuarios hay logueados** actualmente:
```bash
finger
pinky
users
```

Cuando ha accedido cada usuario por última vez:
```bash
lastlog
```

¿Qué puedo **hacer como sudo**?
```bash
sudo -l
```

Comprobar quién tiene privilegios elevados y qué pueden hacer con esos privilegios:
```bash
cat /etc/sudoers
```

# Software instalado
Paquetes instalados en distribuciones basadas en **Debian**
```bash
dpkg -l
```

Paquetes instalados en distribuciones basadas en **Red Hat**:
```bash
rpm -qa
```








# Agradecimientos
byte-mind.net - https://byte-mind.net/enumeracion-y-escalado-de-privilegios-en-linux/





