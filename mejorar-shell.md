# Mejorar una shell

## Si tienes python disponible ...

1. Ejecuta: 
```bash
python3 -c 'import pty; pty.spawn("/bin/bash")'
```

2. Para conseguir que nuestra shell no se cierre con CTRL-C y podamos hacer cosas como usar la teclas flecha y hacer clear, debemos:

    1. Pulsa Ctrl + z para mandar la sesión a background
    2. Ejecuta
    ```ssh
    stty raw -echo; fg
    ```
    3. Pulsa INTRO para traer la sesión a foreground (fg)
    4. Ejecuta:
    ```bash
    stty rows 29 columns 126
    export TERM=screen
    ```