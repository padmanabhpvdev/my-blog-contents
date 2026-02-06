If you've ever worked with addressable LEDs, you're likely familiar with the WS2812B (NeoPixel). However, when your project demands higher density or control over multiple RGB clusters from a single chip, the TM1812 is a powerhouse worth exploring.

In this post, we’ll break down the circuit schematic for a 4-channel RGB setup and explain why this chip is a favorite for custom RGB LED bulbs.

#### **What is TM1812 IC ?**
The TM1812 is an integrated circuit designed specifically for LED driving. Unlike its smaller cousins that control a single RGB pixel, the TM1812 features 12 output channels, allowing it to drive four individual RGB LEDs independently.

**Key Features:**
- **Operating Voltage**: Typically +5V to +24V (This circuit uses +5V logic rail).
- **Single-wire Data**: Uses a return-to-zero protocol, similar to WS2811/WS2812.
- **Cascadable**: Data flows in through DIN and out through DO, allowing you to chain hundreds of these chips together.

##### **TM1812 IC Pinout**
![TM1812 IC Pinout](https://www.hida-led.com/uploads/TM1812-IC-Componenets-for-RGBww-PIXEL-led-strip.jpg)

#### **Circuit Diagram**
![TM1812 LED Driver Circuit](TM1812(circuit).jpg)

##### **Components Used**
| Parts | Label | Quantity |
|----|----|----|
|TM1812 SMD IC| U1 |1|
|RGB LED|D1,D2,D3,D4|4|
|100R 1/4W|R1, R2|2|
|100nF (104) Cap|C1|1|
|1*3P Connector Pin|P1,P2|2|

#### **Circuit Breakdown**
**1. Power and Filtering**
  - **VDD & GND**: The chip is powered by a +5V line.
  - **Decoupling Capacitor**: Note the 100nF capacitor (C1) placed between VDD and GND. This is critical for filtering out high-frequency noise caused by the rapid switching of the LEDs.

**2. The LED Matrix**
  - **Channels 1 & 2**: Controlled via pins 10-15.
  - **Channels 3 & 4**: Controlled via pins 3-8. The LEDs are wired in a Common Anode configuration, where the positive terminals are tied to the +5V rail and the TM1812 sinks the current to ground to light them up.

**3. Signal Integrity**
  - **Resistors (R1, R2)**: 100$\Omega$ resistors are used on the data lines. These act as "termination resistors" to prevent signal reflections and protect the IC from voltage spikes over long data wires.

#### **PCB Layout**
![Front View](TM1812(front).jpg)

*Top View of PCB Layout*

![Back View](TM1812(bottom).jpg)

*Bottom View of PCB Layout*
