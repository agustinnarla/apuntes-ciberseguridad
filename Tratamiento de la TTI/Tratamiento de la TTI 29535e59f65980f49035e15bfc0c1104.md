# Tratamiento de la TTI

Una vez ingresado a la maquina victima vamos a hacer los siguientes pasos 

```bash
script /dev/null -c bash 
stty raw -echo; fg
reset xterm
stty rows 62 columns 248
export TERM=xterm
export SHELL=bash
```