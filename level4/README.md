## Level 4

![Solucion](https://github.com/laugarci/NetPractice/blob/main/level4/level4.png)

### CASO 1:


En esta configuración, tienes dos routers (R1 y R2) y dos máquinas (Machine A y Machine B) que necesitan comunicarse entre sí. Los routers actúan como intermediarios que enrutan el tráfico entre las máquinas. Aquí está cómo funciona:

Machine A a Machine B: Cuando Machine A necesita comunicarse con Machine B, envía un paquete de datos. Este paquete se envía primero a la puerta de enlace predeterminada de Machine A, que es la dirección IP de R1 (23.84.10.126) debido a la ruta "default" configurada en Machine A.

Router R1: R1 recibe el paquete de Machine A. Dado que R1 está configurado con la interfaz A1 con la dirección IP 23.84.10.125 y la máscara de 255.255.255.128, Machine A y R1 están en la misma subred. R1 sabe que Machine B no está en su misma subred, por lo que el paquete se reenvía al router R2.

Router R2: El paquete llega a R2 a través de la interfaz B1. Dado que R2 está configurado con la interfaz B1 con la dirección IP 170.95.213.253 y la máscara de 255.255.192.0, Machine B y R2 están en la misma subred. R2 sabe cómo llegar a Machine B, por lo que entrega el paquete a Machine B.

Machine B: Machine B recibe el paquete y procesa la información.

Este proceso permite que Machine A y Machine B se comuniquen entre sí a través de los routers R1 y R2. El tráfico fluye desde Machine A a R1, luego de R1 a R2 y finalmente de R2 a Machine B. Las rutas "default" configuradas en Machine A y Machine B son esenciales para dirigir el tráfico a través de los routers cuando las máquinas necesitan comunicarse con dispositivos fuera de su propia subred.

**Interface R1:**
- IP: 23.84.10.126
- Máscara: 255.255.255.128

**Interface A1:**
- IP: 23.84.10.125
- Máscara: 255.255.255.128

**Client A: Machine A Routes:**
- default -> 23.84.10.126
  
**Interface R2:**
- IP: 170.95.213.254
- Máscara: 255.255.192.0

**Interface B1:**
- IP: 170.95.213.253
- Máscara: 255.255.192.0

**Client B: Machine B Routes:**
- default -> 170.95.213.254
