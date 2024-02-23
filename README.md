# Random_Number_Generator
Random Number Generator
![426195809_919338070193592_7939037188568230287_n](https://github.com/Wneq1/Random_Number_Generator/assets/127328405/0b00f99c-bdb6-48a3-b5a8-f25ea270181f)
This project is part of a series of nonsensical projects. I built it inspired by the link:
https://www.youtube.com/watch?v=1ldxJn_07gs&t=1s
This circuit functions as a machine that randomly selects digits ranging from 0 to 9 and presents it on 7seg- display, influenced by elements such as contact vibrations, temperature, and room lighting.
Components you will need to build this project:
Resistors:
• 10kΩ x 1
• 510 Ω x 7
• 100kΩ x 1
• Photoresistor 10kΩ x 1
• Thermistor 10kΩ x 1
Capacitor 100nF x 1 (excluding bypass capacitors)
Pushbutton x 1
CD4026 x 1
CD4046 x 1
7-segment display 5161AS (common cathode) x 1

Our circuit consists of a 7-segment display, the operation of which does not need to be explained, controlled by a dedicated driver CD4026, which we will take a closer look at.
![image](https://github.com/Wneq1/Random_Number_Generator/assets/127328405/871ee40a-6808-4212-b1c8-4fc71f60851a)

Pin Description:
1.Clock – Input for the clock signal, a square wave signal is provided here, and when there is a transition from 0 to 1 (rising edge), the counter increments.
2.Clock inhibit - Clock inhibition; if a logic 1 is applied, the circuit does not count, while with a logic 0, the circuit counts.
3.Display enable – Enables the display; logic 0 turns off the display, while logic 1 turns it on.
4.Display enable out – Signal for disabling the display, used for communication with other circuits.
5.Carry out - Carry output; two states are present: 1 for values 0-4 and 0 for 5-9. When transitioning from 9 to 0, a rising edge occurs, which can be used to trigger the next CD4026 circuit.
6.Segment outputs - Activating the corresponding segment is achieved by setting the output to logic 1.
7.Power supply: Pin 8 (GND), Pin 16 (Vcc).
8.Reset - Reset input causing the counter to return to state 0.
Another component is the CD4046 circuit, which is a phase-locked loop circuit, but for our purposes, we are only interested in the VCO (voltage-controlled oscillator) generator, which can be tuned by voltage.
![image](https://github.com/Wneq1/Random_Number_Generator/assets/127328405/e8bb6159-6640-4ed0-a30c-75c33f0544c4)
We will only be using some of the pins of our generator:
1.VCO Out – Output from our generator (square wave signal).
2.C1A, C1B – Pins to which we connect the capacitor.
3.R1 – Resistor used to select the minimum frequency (fmin).
4.R2 – Resistor used to select the maximum frequency (fmax).
5.VCO In – Voltage input for tuning our signal.
6.Inhibit – Input for enabling our generator.
