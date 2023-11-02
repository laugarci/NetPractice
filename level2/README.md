## Level 2

![Solucion](https://github.com/laugarci/NetPractice/blob/main/level2/level2.png)

### CASO 1:

Para que un cliente pueda comunicarse con el otro, debemos asegurarnos de que ambos estén en la misma red, lo que significa que deben compartir los mismos primeros bloques de la dirección IP, teniendo en cuenta la máscara de subred.

**Interface A1:**
- IP: 192.168.134.200
- Máscara: 255.255.255.224

**Interface B1:**
- IP: 192.168.134.222
- Máscara: 255.255.255.224

### CASO 2:

Para una máscara de /30, que equivale a 255.255.255.252 en notación decimal, solo hay 2 direcciones IP utilizables en la subred. Por lo tanto, las direcciones IP deben estar dentro de ese rango.

**Interface C1:**
- IP: 192.168.1.1
- Máscara: /30 (255.255.255.252)

**Interface D1:**
- IP: 192.168.1.2
- Máscara: /30 (255.255.255.252)
