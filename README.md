# Rhino Mini 4808
Homemade ATmega4808 Board (Arduino Compatible)

#### Summary
- Breadboard oriented minimal design
- 3 UART ports
- 1600mil * 700mil 2-Layer PCB
- Compliant with SparkFun FTDI Basic Breakout

#### Usage
The original Serial2 port is used by the 32.768kHz quartz crystal circuit. When using Serial2, the following code must be written.
```
// UART pin swapping
Serial2.swap(1);
Serial2.begin(9600);
```

#### Arduino IDE Setup
- Install [MegaCoreX](https://github.com/MCUdude/MegaCoreX) to Boards Manager
- Select MegaCoreX > ATmega4808 as Board
- Select Board connected COM port as Port
- Select Optiboot (UART0 default pins) as Bootloader
- Select 32 pin standard as Pinout
- Select SerialUPDI (57600 baud) as Programmer
- Other items should be set appropriately

#### Wiring
```
To burn the Bootloader:
+------------+                 +------------+
| USB-Serial |                 | Rhino Mini |
|            |                 |            |
|        RXD +--------+--470R--+ UPDI       |
|            |        |        |            |
|        TXD +---|<---+        |            |
|            | 1N4148          |            |
|        GND +-----------------+ GND        |
|            |                 | GND        |
|        VCC +-----------------+ VCC        |
|            |                 | RXD        |
|            |                 | TXD        |
|            |                 | DTR        |
+------------+                 +------------+
```

```
To upload a Sketch:
+------------+     +------------+
| USB-Serial |     | Rhino Mini |
|            |     |            |
|            |     | UPDI       |
|        GND +-----+ GND        |
|        CTS +-----+ GND        |
|        VCC +-----+ VCC        |
|        TXD +-----+ RXD        |
|        RXD +-----+ TXD        |
|        DTR +-----+ DTR        |
+------------+     +------------+
```
