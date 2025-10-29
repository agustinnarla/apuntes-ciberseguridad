# Borazuwarahctf

Dificultad: Muy Facil
Tecnicas: Steghide - Exiftool - Hydra
Pagina: Docker labs
Estado: Listo

# 

```bash
Lo primero que hacemos es ver q puertos están abiertos 

nmap -p- -—open —min-rate 5000 -vvv -n -Pn 172.17.0.2 -oG allport
```

![image.png](image.png)

```bash
Luego tiramos unos script basicos y buscamos las versiones de los puertos abiertos 

nmap -p22,80 -sCV -oN targeted 172.17.0.2
```

![image.png](image%201.png)

```bash
Al abrir la web, vemos que tenemos una imagen, por lo que decidimos descargarla.
```

![image.png](image%202.png)

```bash
Vamos a utilizar steghide para extraer los datos de la imagen y vemos que tenemos un archivo secreto
```

![image.png](image%203.png)

```bash
Ahora vamos a utilizar exiftool para impeccionar los metadatos 
```

![image.png](image%204.png)

```bash
Al encontrar un usuario borazuwarah, decidimos aplicar hydra para ver encontrar su contraseña 
```

![image.png](image%205.png)

```bash
Y encontramos la contraseña -> 1234567

Ingresamos mediante ssh con el usuario y contraseña correspondiente 
```

# Subida de Privilegio

![image.png](image%206.png)

```bash

Una vez ingresado como borazuwarah, vamos a usar sudo -l para ver si tenemos alguna forma de elevar nuestro privilegio
```

![image.png](image%207.png)

```bash
Vemos que podemos ejecutar el binario bash por lo que nos respaldamos en gtfobins y elevamos nuestro privilegio
```

![image.png](image%208.png)