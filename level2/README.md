## Level 2

![Solucion](https://github.com/laugarci/NetPractice/blob/main/level2/level2.png)

### CASO 1:

Para que un cliente pueda comunicarse con el otro, debemos asegurarnos de que ambos estén en la misma red, lo que significa que deben compartir los mismos primeros bloques de la dirección IP, teniendo en cuenta la máscara de subred.

Si tienes la dirección IP 192.168.134.222 y la máscara de subred 255.255.255.224, puedes calcular los rangos de IP válidos para esta subred de la siguiente manera:

- Encuentra la dirección de red: realiza una operación AND lógica entre la dirección IP y la máscara de subred. Esto te dará la dirección de red.
```
Dirección IP: 11000000.10101000.10000110.11011110
Máscara de subred: 11111111.11111111.11111111.11100000
Dirección de red: 11000000.10101000.10000110.11000000 (192.168.134.192)
```
- Encuentra la dirección de difusión: invierte los bits de la máscara de subred y realiza una operación OR lógica con la dirección de red. Esto te dará la dirección de difusión.
```
Máscara invertida: 00000000.00000000.00000000.00011111
Dirección de red: 11000000.10101000.10000110.11000000
Dirección de difusión: 11000000.10101000.10000110.11011111 (192.168.134.223)
```
Los rangos de IP válidos son todas las direcciones IP entre la dirección de red y la dirección de difusión, excluyendo estas dos direcciones. En este caso, los rangos válidos son desde 192.168.134.193 hasta 192.168.134.222.

**Interface A1:**
- IP: 192.168.134.200
- Máscara: 255.255.255.224

**Interface B1:**
- IP: 192.168.134.222
- Máscara: 255.255.255.224

### CASO 2:

Si tienes una máscara de red de 255.255.255.252, significa que solo hay 2 direcciones IP válidas en esa subred, ya que esta máscara reserva 2 bits para la parte de host.

- Encuentra la dirección de red: Realiza una operación AND lógica entre la dirección IP y la máscara de red. Esto te dará la dirección de red.
```
Dirección IP: (por ejemplo, 192.168.1.0)
Máscara de red: 255.255.255.252
```

La dirección de red se obtiene al realizar la operación & (AND):
```
Dirección IP: 11000000.10101000.00000001.00000000
Máscara de red: 11111111.11111111.11111111.11111100
Dirección de red: 11000000.10101000.00000001.00000000
```

- Encuentra la dirección de difusión: La dirección de difusión en una subred /30 se obtiene al sumar 3 a la dirección de red. La dirección de difusión es la última dirección válida.
```
Dirección de red: 192.168.1.0
Dirección de difusión: 192.168.1.3
```

Ahora, tienes dos direcciones IP válidas en esta subred:
```
Dirección de red: 192.168.1.0
Primer host: 192.168.1.1
Segundo host: 192.168.1.2
Dirección de difusión: 192.168.1.3
```

Puedes asignar cualquier dirección IP dentro de este rango a dispositivos en esta subred. Por ejemplo, podrías utilizar la dirección 192.168.1.1 para un dispositivo y la dirección 192.168.1.2 para otro dispositivo, dejando la dirección de red y la dirección de difusión reservadas para fines de identificación de la subred.

**Interface C1:**
- IP: 192.168.1.1
- Máscara: /30 (255.255.255.252)

**Interface D1:**
- IP: 192.168.1.2
- Máscara: /30 (255.255.255.252)
