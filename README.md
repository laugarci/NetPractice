# NetPractice

## Direcciones IP IPv4

Las direcciones IP son números que se utilizan para identificar dispositivos en una red. En el caso de IPv4, estas direcciones constan de 32 bits, lo que significa que están compuestas por 32 dígitos binarios (0 y 1). Para facilitar la representación, las direcciones IP se dividen en 4 grupos de 8 bits, a menudo llamados "bloques" o "octetos". Cada uno de estos bloques se representa en notación decimal y varía desde 0 hasta 255. Cada bloque puede tener un valor mínimo de 0 y un valor máximo de 255.

## Máscara de red IPv4

La máscara de red se utiliza para determinar qué parte de una dirección IP identifica la red y qué parte identifica los dispositivos dentro de esa red. Se representa de manera similar a las direcciones IP, con 32 bits. En una máscara de red, los bits se dividen en dos partes: unos consecutivos y ceros consecutivos. Los unos representan la parte de la red, y los ceros representan la parte de los dispositivos en esa red.

La característica especial de la máscara de red es que, una vez que un bit se convierte en 0, no puede haber más bits con valor 1 en los bloques subsiguientes. Esto se debe a que los bloques contiguos de unos indican la parte de la red y, cuando se encuentran ceros, se delimita la parte de los dispositivos.

Para que dos dispositivos puedan enviarse paquetes entre sí en una red, deben estar en la misma red o estar conectados a través de un enrutador que pertenezca a ambas subredes. En otras palabras, para la comunicación directa entre dispositivos, deben compartir los mismos primeros bloques de la dirección IP que están definidos por la máscara de red.

## IPs especiales

#### Network privadas:

Las Network privadas son redes que están configuradas de manera que no están directamente conectadas a Internet y, por lo tanto, no son accesibles desde el Internet público. Estas redes se utilizan comúnmente en entornos empresariales, educativos y domésticos para crear un espacio de red aislado donde los dispositivos pueden comunicarse entre sí.
Estos rangos de IPs estan reservadas para Networks privadas:
```
10.0.0.0 – 10.255.255.255
172.16.0.0 – 172.31.255.255
192.168.0.0 – 192.168.255.255
```
#### Direcciones loopback:

Las loopback son direcciones IP especiales que se utilizan para permitir que un ordenador se comunique con sí mismo. Cuando un ordenador envía datos a la dirección IP loopback, esos datos se redirigen internamente al propio dispositivo. Esto es útil para probar la funcionalidad de red de un ordenador sin necesidad de una conexión de red real.

Estos rangos de IPs estan reservads para las direcciones loopback:
```
127.0.0.0 – 127.255.255.255
```


