# NetPractice

# NetPractice README

## Índice

1. [Direcciones IP IPv4](#direcciones-ip-ipv4)
2. [IPs especiales](#ips-especiales)
3. [Máscara de red IPv4](#máscara-de-red-ipv4)
4. [Routers y Switches](#routers-y-switches)
5. [Tabla de enrutamiento](#tabla-de-enrutamiento)
6. [Red (Network)](#red-network)
7. [Solución de Net Practice](#solución-de-net-practice)


## Direcciones IP IPv4

Las direcciones IP son números que se utilizan para identificar dispositivos en una red. En el caso de IPv4, estas direcciones constan de 32 bits, lo que significa que están compuestas por 32 dígitos binarios (0 y 1). Para facilitar la representación, las direcciones IP se dividen en 4 grupos de 8 bits, a menudo llamados "bloques" o "octetos". Cada uno de estos bloques se representa en notación decimal y varía desde 0 hasta 255. Cada bloque puede tener un valor mínimo de 0 y un valor máximo de 255. Esto significa que cada bloque de 8 bits puede variar de 0 a 255.

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

## Máscara de red IPv4

La máscara de red se utiliza para determinar qué parte de una dirección IP identifica la red y cuál identifica los dispositivos dentro de esa red. Se representa en 32 bits, y los bits se dividen en dos partes: unos consecutivos y ceros consecutivos. Los unos indican la parte de la red, y los ceros indican la parte de los dispositivos en la red.

La característica especial de la máscara de red es que, una vez que un bit se vuelve 0, no puede haber más bits con valor 1 en los bloques subsiguientes. Esto se debe a que los bloques de unos indican la parte de la red y, cuando se encuentran ceros, se delimita la parte de los dispositivos.

La elección de la máscara de red afecta la cantidad de direcciones IP utilizables en una subred y la cantidad de subredes que se pueden crear. Cuanto más pequeña es la máscara (menos bits se reservan para la red), más direcciones IP se pueden utilizar en una subred, pero se pueden crear menos subredes. Por otro lado, una máscara más grande permite más subredes, pero con menos direcciones IP utilizables en cada una.

| CIDR | Notación de punto decimal | Número de direcciones IP por subred | Direcciones IP utilizables por subred | Número de subredes |
|------|----------------------------|------------------------------------|--------------------------------------|---------------------|
| /32  | 255.255.255.255            | 1                                  | 0                                    | 256                 |
| /31  | 255.255.255.254            | 2                                  | 0                                    | 128                 |
| /30  | 255.255.255.252            | 4                                  | 2                                    | 64                  |
| /29  | 255.255.255.248            | 8                                  | 6                                    | 32                  |
| /28  | 255.255.255.240            | 16                                 | 14                                   | 16                  |
| /27  | 255.255.255.224            | 32                                 | 30                                   | 8                   |
| /26  | 255.255.255.192            | 64                                 | 62                                   | 4                   |
| /25  | 255.255.255.128            | 128                                | 126                                  | 2                   |
| /24  | 255.255.255.0              | 256                                | 254                                  | 1                   |


Para que dos dispositivos puedan enviarse paquetes entre sí en una red, deben estar en la misma red o estar conectados a través de un enrutador que pertenezca a ambas subredes. En otras palabras, para la comunicación directa entre dispositivos, deben compartir los mismos primeros bloques de la dirección IP definidos por la máscara de red.

## Routers y Switches

### Switches

Un switch es un dispositivo de red que se utiliza para conectar múltiples dispositivos dentro de una misma red local (LAN). Su función principal es la de distribuir paquetes de datos entre estos dispositivos. En una red, los dispositivos, como ordenadores, impresoras y servidores, se conectan a un switch para poder comunicarse entre sí. El switch toma los datos que provienen de un dispositivo y los envía al dispositivo de destino correcto en la red, lo que mejora la eficiencia y la velocidad de la comunicación dentro de la LAN.
Los switches operan en la capa de enlace de datos del modelo OSI y utilizan direcciones MAC (Media Access Control) para determinar a qué dispositivo debe entregarse un paquete.
Los switches se utilizan en redes locales, como en oficinas o casas. Son ideales para redes donde se necesita un alto tráfico de datos entre dispositivos en la misma red.

### Routers

Un router es un dispositivo que se utiliza para conectar diferentes redes entre sí. Su función principal es la de dirigir paquetes de datos entre estas redes, lo que permite la comunicación entre dispositivos en redes separadas.
Los routers operan en la capa de red del modelo OSI y utilizan direcciones IP para determinar cómo dirigir los paquetes de datos de una red a otra. Son esenciales para la conectividad entre redes, como la conexión de la red local a Internet.
Un router puede ser parte de múltiples redes y utiliza sus interfaces para conectarse a cada una de ellas. Por ejemplo, un router puede estar conectado a la red local (LAN) y a Internet a través del proveedor de servicios de Internet (ISP).
Los routers son responsables de tomar decisiones sobre la mejor ruta para enviar paquetes de datos y de garantizar que los paquetes lleguen a su destino correcto. Además, pueden realizar funciones de seguridad, como el filtrado de paquetes no deseados.

En resumen, los **switches** se utilizan para conectar múltiples dispositivos en una misma red local y facilitar la comunicación dentro de esa red, mientras que los **routers** se utilizan para conectar diferentes redes entre sí, dirigir paquetes de datos y permitir la comunicación entre redes separadas, incluida la conexión a Internet.

## Tabla de enrutamiento

La función principal de la tabla de enrutamiento es almacenar información sobre cómo dirigir paquetes de datos desde un dispositivo a su destino a través de la red.

### Destino
El "destino" se refiere a la dirección de red a la que se quiere enviar un paquete de datos. Esto podría ser una red específica dentro de la infraestructura de la red, identificada por su dirección IP y su máscara. 
Si no se quiere especificar una dirección de destino en particular, se puede utilizar una entrada especial denominada "predeterminado" o "default". Esta entrada se utiliza para dirigir todos los paquetes de datos que no coinciden con ninguna otra entrada en la tabla de enrutamiento.

### Next hop

El "next hop" es la dirección del siguiente enrutador al que se deben enviar los paquetes de datos para alcanzar la red de destino. En esencia, indica el próximo dispositivo o enrutador en la ruta que se debe seguir para entregar los paquetes a su destino final. El "next hop" es la próxima parada en el camino hacia la red de destino.

### Función de la tabla de enrutamiento

Cuando un dispositivo, como un router, recibe un paquete de datos que debe transmitirse a través de la red, consulta su tabla de enrutamiento para determinar cómo dirigir el paquete. El dispositivo busca una entrada en la tabla de enrutamiento que coincida con la dirección de destino del paquete y luego utiliza la información del "next hop" para enviar el paquete al siguiente enrutador en el camino hacia su destino.

En resumen, la tabla de enrutamiento es una herramienta esencial que permite a los dispositivos de red, como routers, determinar cómo enrutar eficazmente los paquetes de datos hacia su destino. Al almacenar información sobre destinos y próximos saltos, la tabla de enrutamiento facilita la toma de decisiones sobre cómo se deben dirigir los datos a través de la red. Cada entrada en la tabla representa una ruta específica a una red o el camino predeterminado para los paquetes sin una coincidencia exacta en la tabla.

## Red (Network)

Una red es un conjunto de dispositivos de computación interconectados que pueden comunicarse entre sí para compartir información y recursos. Estos dispositivos pueden incluir ordenadores, servidores, impresoras, routers...

Para tener una red que funcione correctamente, es necesario aplicar todos los componentes mencionados anteriormente. Esto significa que todos los dispositivos deben estar configurados y conectados de manera adecuada en la red.

La comunicación efectiva en una red requiere que los dispositivos estén conectados, ya sea directamente entre sí o a través de routers que formen parte de ambas redes. Los routers desempeñan un papel crucial al conectar redes separadas y permitir que los dispositivos de una red se comuniquen con los de otra.

Para determinar si dos dispositivos están en la misma red, se realiza una operación lógica de tipo "Y" bit a bit entre la dirección IP y la máscara de subred de cada dispositivo: 
- Primero, se convierten las direcciones IP y las máscaras de subred a su equivalente en formato binario (ceros y unos).
- Luego, se realiza una operación "&" bit a bit entre los bits correspondientes de la dirección IP y la máscara de subred. Si ambos bits son "1", el bit correspondiente en la dirección de red resultante es "1"; en cualquier otro caso, el bit resultante es "0".

**Ejemplo:**

Si tienes una dirección IP de "192.168.100.1" y una máscara de subred de "255.255.255.0", realizas la operación de tipo "&" bit a bit y obtienes la dirección de red "192.168.100.0".

Si dos dispositivos comparten la misma dirección de red, significa que están en la misma red y pueden comunicarse entre sí de manera directa, sin necesidad de enrutadores. La dirección de red es lo que identifica la red a la que pertenecen.

## Solución de Net Practice

- [Level 1](https://github.com/laugarci/NetPractice/tree/main/level1)
- [Level 2](https://github.com/laugarci/NetPractice/tree/main/level2)
- [Level 3](https://github.com/laugarci/NetPractice/tree/main/level3)

