# Rhino Mini 4808
Homemade ATmega4808 Board (Arduino Compatible)

- Breadboard oriented minimal design
- 3 USART ports
- 1600mil * 700mil 2-Layer PCB

The original Serial2 port is used by the 32.768kHz quartz crystal circuit. When using Serial2, the following code must be written.
```
// UART pin swapping
Serial2.swap(1);
Serial2.begin(9600);
```
