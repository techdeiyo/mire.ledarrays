# LED Sequence Project

This project demonstrates how to control a sequence of LEDs using an Arduino. The LEDs will light up in a pattern, first from the lowest pin to the highest and then back from the highest pin to the lowest.

## Components Required

- Arduino board (e.g., Uno, Nano)
- 6 LEDs
- 6 resistors (220 ohms each)
- Breadboard
- Jumper wires

## Circuit Diagram

1. Connect each LED to one of the following digital pins: 2, 3, 4, 5, 6, and 7 on the Arduino.
2. Connect the longer leg (anode) of each LED to the corresponding pin.
3. Connect the shorter leg (cathode) of each LED to one end of a 220-ohm resistor.
4. Connect the other end of each resistor to the GND (ground) pin on the Arduino.

## Code Explanation

### Variables

- **`int timer = 100;`**: This variable controls the delay time between LED transitions. A higher value results in slower LED sequences.
- **`int ledPins[] = {2, 7, 4, 6, 5, 3};`**: This array stores the pin numbers where each LED is connected.
- **`int pinCount = 6;`**: This variable holds the number of pins (i.e., the number of LEDs).

### Setup

- **`void setup()`**: The `setup()` function runs once when the program starts. Inside this function:
  - A `for` loop is used to iterate through each pin in the `ledPins` array, setting each as an output using `pinMode()`.

### Loop

- **`void loop()`**: The `loop()` function runs continuously after `setup()`. Inside this function:
  - **First Loop**:
    - A `for` loop iterates from the lowest to the highest pin in the `ledPins` array.
    - **`digitalWrite(ledPins[thisPin], HIGH);`**: This turns on the current LED.
    - **`delay(timer);`**: This pauses the program for the duration specified by the `timer` variable.
    - **`digitalWrite(ledPins[thisPin], LOW);`**: This turns off the current LED.
  - **Second Loop**:
    - Another `for` loop iterates from the highest to the lowest pin in the `ledPins` array, reversing the LED sequence.
    - The same steps as in the first loop are repeated to light up and turn off the LEDs in reverse order.

## How to Use

1. Connect your Arduino board to your computer.
2. Open the Arduino IDE.
3. Copy and paste the provided code into a new sketch.
4. Upload the sketch to your Arduino board.
5. Watch the LEDs light up sequentially from one end to the other and then back again.

## Customization

- Adjust the `timer` variable to speed up or slow down the LED sequence.
- Modify the `ledPins` array to change the order or number of LEDs in the sequence.

## License

This project is open-source and available under the [MIT License](LICENSE).

---

Enjoy creating dynamic LED sequences with Arduino!
