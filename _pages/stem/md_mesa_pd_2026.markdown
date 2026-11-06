---
layout: single
title: "Maryland MESA Teacher PD 2026: Arduino Training Stations"
subtitle:
permalink: /stem/md_mesa_pd_2026.html
author_profile: true
share: true
---


Thank you to all of the teachers for joining us for the Maryland MESA Teacher
PD 2026! This page collects the Arduino examples from each training station so
you can revisit them, try them in the Tinkercad simulator, and rebuild them in
your own classroom. If you have any questions, please reach out through the
Maryland MESA team.

Each station below links to a Tinkercad project. Two of the four can be
simulated. The other two are a reference for the wiring and the code.

| Station         | Topic              | Simulates in Tinkercad? |
|-----------------|--------------------|-------------------------|
| [A](#station-a) | Button Press       | ✅ Yes                   |
| [B](#station-b) | Distance Sensor    | ❌ No                    |
| [C](#station-c) | Temperature Sensor | ❌ No                    |
| [D](#station-d) | Light Sensor       | ✅ Yes                   |

---

## MESA Training Station A - Button Press
{: #station-a}

A first Arduino project that shows how a pushbutton controls outputs. Press the
button and the LED lights up while the buzzer plays a 440 Hz tone. Let go and
both turn off. The sketch uses the Arduino's internal pull-up resistor, so the
button only needs to connect between the input pin and ground, with no external
resistor. This is a good introduction to digital input, digital output, and
`if`/`else` logic.

**Simulation:** ✅ This project runs in the Tinkercad simulator.

**What you'll need:** Arduino Uno, breadboard, pushbutton, LED with a
current-limiting resistor, piezo buzzer, jumper wires.

[Open Station A in Tinkercad](https://www.tinkercad.com/things/4E7ejJIyPGW-mesatrainingstationa?sharecode=NRqtkEiy30053d-tpsPWYdj8m4H8ySwrY6uLpCkgVCY){:target="_blank" rel="noopener"}

---

## MESA Training Station B - Distance Sensor
{: #station-b}

An ultrasonic sensor measures how far away an object is. When something comes
within 20 cm, the LED lights up and the buzzer sounds. The sketch includes a
documented `getDistance()` function that explains how the sensor's echo time is
converted into centimeters, and it returns a negative value when a reading
fails. This is a good example for teaching functions, sensors, unit conversion,
and the speed of sound.

**Simulation:** ❌ This project does not work in the Tinkercad simulator. The
simulated ultrasonic sensor seems to be buggy, and the sketch always reports a
failed reading, so the LED and buzzer never turn on. The project is there as a
reference for the wiring and the code.

**What you'll need:** Arduino Uno, breadboard, HC-SR04 style ultrasonic sensor
(4 pins), LED with a current-limiting resistor, piezo buzzer, jumper wires.

[Open Station B in Tinkercad](https://www.tinkercad.com/things/kCcnrIdk6CM-mesatrainingstationb?sharecode=W0tSs7DwyZEAOxsiqJC_L2SQYQvp-RvDFBdxpYS8Xh0){:target="_blank" rel="noopener"}

---

## MESA Training Station C - Temperature Sensor
{: #station-c}

A DHT11 sensor reads the temperature once per second and prints it to the
Serial Monitor. A green LED shows that the temperature is below 30 °C, and a
red LED lights up at or above it. The sketch checks each reading and reports an
error if the sensor read fails, instead of acting on bad data. This is a good
example for teaching sensor libraries, error checking, and threshold alerts.

**Simulation:** ❌ This project does not simulate in Tinkercad. The sketch needs
a custom library for the DHT sensor, and Tinkercad does not support it. The
project is there as a reference for the wiring and the code, and it works on
real hardware once the library is installed.

**What you'll need:** Arduino Uno, breadboard, DHT11 temperature and humidity
sensor, red and green LEDs with current-limiting resistors, jumper wires, and
the `dht` library used by the sketch.
<!-- TODO: add the exact library name and a link to it here -->

[Open Station C in Tinkercad](https://www.tinkercad.com/things/kVsjMuEN93Q-mesatrainingstationc?sharecode=13cOQyCfcMmUhpe91xxxfTkTHIxSq_ICcpRcPh_EPws){:target="_blank" rel="noopener"}

---

## MESA Training Station D - Light Sensor
{: #station-d}

A light sensor measures brightness. When it gets too bright, a servo deploys a
shade, and the shade retracts when the light dims. The sketch converts the
sensor reading into a percentage and uses two thresholds (close at 95%, reopen
at 90%) so the servo does not jitter when the light level is near the cutoff.
The Serial Monitor shows live readings, which students can use to calibrate the
sensor for their own setup. This is a good example for teaching analog input,
mapping values, servos, and hysteresis.

**Simulation:** ✅ This project runs in the Tinkercad simulator. The
calibration values in the sketch were measured on real hardware, so in the
simulator and with your own sensor, watch the Serial Monitor and adjust the
minimum and maximum values to match.

**What you'll need:** Arduino Uno, breadboard, photoresistor (light sensor) with
a fixed resistor for a voltage divider, small hobby servo, jumper wires.

[Open Station D in Tinkercad](https://www.tinkercad.com/things/932VtjVzPQv-mesatrainingstationd?sharecode=7aRNtE1ilJy0HeeZCW0Unbgyj6snVw35ueYcWcp2TE4){:target="_blank" rel="noopener"}

---

## Resources

### Where to buy parts

- **[Adafruit](https://www.adafruit.com/)** has beginner-friendly product pages
  with good photos, guides, and wiring diagrams. It also runs the
  [Adafruit Learning System](https://learn.adafruit.com/).
- **[SparkFun](https://www.sparkfun.com/)** has similar beginner-friendly parts
  and a library of tutorials at [learn.sparkfun.com](https://learn.sparkfun.com/).
- **[DigiKey](https://www.digikey.com/)** has a huge selection at good prices,
  but it is a little more advanced to search. Part listings are organized by
  detailed specifications, and picking the right one takes some understanding
  of electronics. It is a good option once you are comfortable reading a
  datasheet.

### Arduino documentation

Start with the [Arduino Language Reference](https://docs.arduino.cc/language-reference/),
which documents every function used in these examples, and the
[Arduino Learn](https://docs.arduino.cc/learn/) section for tutorials. The
[Arduino IDE](https://www.arduino.cc/en/software) is a free download. To try
sketches without hardware, use [Tinkercad Circuits](https://www.tinkercad.com/circuits).

Here are the functions used at each station, with links to their reference
pages:

**Used in every station**

- [`pinMode()`](https://docs.arduino.cc/language-reference/en/functions/digital-io/pinMode/):
  sets a pin as an input or output
- [`digitalWrite()`](https://docs.arduino.cc/language-reference/en/functions/digital-io/digitalWrite/):
  turns an output pin on or off

**Station A - Button Press**

- [`digitalRead()`](https://docs.arduino.cc/language-reference/en/functions/digital-io/digitalRead/):
  reads whether an input pin is on or off
- [`tone()`](https://docs.arduino.cc/language-reference/en/functions/advanced-io/tone/)
  and [`noTone()`](https://docs.arduino.cc/language-reference/en/functions/advanced-io/noTone/):
  start and stop a tone on a buzzer

**Station B - Distance Sensor**

- [`pulseIn()`](https://docs.arduino.cc/language-reference/en/functions/advanced-io/pulseIn/):
  measures how long a pulse lasts
- [`delayMicroseconds()`](https://docs.arduino.cc/language-reference/en/functions/time/delayMicroseconds/):
  pauses for a very short time, used here to time the trigger pulse
- [`delay()`](https://docs.arduino.cc/language-reference/en/functions/time/delay/):
  pauses between readings
- `tone()` and `noTone()`, as in Station A

**Station C - Temperature Sensor**

- [`Serial`](https://docs.arduino.cc/language-reference/en/functions/communication/serial/):
  prints values to the Serial Monitor
- `delay()`, as in Station B

**Station D - Light Sensor**

- [`analogRead()`](https://docs.arduino.cc/language-reference/en/functions/analog-io/analogRead/):
  reads a value from 0 to 1023 from an analog pin
- [`map()`](https://docs.arduino.cc/language-reference/en/functions/math/map/):
  converts a value from one range to another
- [`constrain()`](https://docs.arduino.cc/language-reference/en/functions/math/constrain/):
  keeps a value within a minimum and maximum
- [Servo library](https://docs.arduino.cc/libraries/servo/): controls a servo
  motor
- `Serial` and `delay()`, as in Stations B and C