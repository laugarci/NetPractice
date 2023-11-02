
## Level 3

![Solucion](https://github.com/laugarci/NetPractice/blob/main/level3/level3.png)

### CASO 1:

Para que Interface C1 se comunique con Client A y Client B, necesitamos asegurarnos de que todos estén en la misma red. Dado que ya se proporciona la dirección IP y la máscara de Client A, debemos asegurarnos de que las direcciones IP de Interface C1, Client A y Client B estén en la misma subred.

**Interface C1:**
- IP: 104.198.123.1
- Máscara: 255.255.255.128

**Client B:**
- IP: 104.198.123.2
- Máscara: 255.255.255.128

**Client A:**
- IP: 104.198.123.125
- Máscara: 255.255.255.128

Con esta configuración, Interface C1, Client A y Client B están en la misma subred con la dirección IP de rango 104.198.123.X (X puede ser cualquier número en el rango de 0 a 127) y la máscara 255.255.255.128, lo que les permite comunicarse entre sí.
