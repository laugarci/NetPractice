## Level 6

![Solucion](https://github.com/laugarci/NetPractice/blob/main/level6/level6.png)

### CASO 1:

**Interface Somewhere on the Net:**
- IP: 8.8.8.8
- Máscara: /16

**Internet 1: internet. Routes:**
- 91.3.169.224/25 -> 163.172.250.12

**Interface R2:**
- IP: 163.172.250.12
- Máscara: 255.255.255.240

**Router R: gate.non-real.com. Routes:**
- default -> 163.172.250.1

**Interface R1:**
- IP: 91.3.169.226
- Máscara: 255.255.255.128

**Switch S: sw-1.non-real.com**

**Interface A1:**
- IP: 91.3.169.227
- Máscara: 255.255.255.128

**Client A: webserv.non-real.com. Routes:**
- 0.0.0.0/0 -> 91.3.169.226
