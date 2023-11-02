## Level 1

### CASO 1:

![Solucion](https://github.com/laugarci/NetPractice/blob/main/level1/level1.png)

Para que un cliente pueda comunicarse con el otro, debemos asegurarnos de que ambos estén en la misma red, lo que significa que deben compartir los mismos tres primeros bloques de la dirección IP.

En el primer caso:
- **Client A** tiene la dirección IP: 104.93.23.296
- **Client B** tiene la dirección IP: 104.99.23.12

Como Client B ya tiene la dirección IP 104.99.23.12, Client A debe usar una dirección IP en el mismo rango. Podríamos usar, por ejemplo:

- **Client A:** IP: 104.99.23.Y / Máscara: 255.255.255.0

En la IP, **"Y"** es un número válido en el rango de direcciones para la misma red, de 1 a 254, ya que la dirección IP 104.99.23.0 se reserva generalmente como dirección de red y la dirección IP 104.99.23.255 se reserva como dirección de broadcast en una máscara de red con 255.255.255.0.

Al hacer esto, Client A y Client B compartirán los mismos tres primeros bloques (104.99.23) en sus direcciones IP, lo que les permitirá comunicarse en la misma red.
