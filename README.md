
NaCl Concentration Measurement with Arduino
This repository contains an Arduino sketch that measures the concentration of sodium chloride (NaCl) in a solution using an analog sensor. The sketch collects voltage readings, calculates the corresponding NaCl concentration in parts per million (ppm), and provides output control based on the measured concentration.

Features
Analog Input: Reads voltage from an analog sensor connected to pin A0.
Concentration Calculation: Converts voltage readings to NaCl concentration using a defined conversion factor.
Median Calculation: Collects multiple readings and calculates the median for more stable output.
Control Outputs: Uses three output pins (A1, A2, A3) to indicate different concentration levels.
Code Overview
Key Variables
ppmPerVolt: Conversion factor to convert voltage to ppm (106734.4346 ppm/Volt).
medianCalculated: Flag to indicate if the median values have already been calculated.
Setup Function
Initializes the analog input pin (A0) and sets up output pins (A1, A2, A3) for controlling external devices.
Begins serial communication at a baud rate of 9600.
Loop Function
Collects five voltage samples from the sensor if the median has not been calculated.
Converts the raw analog readings to voltage.
Calculates the NaCl concentration in ppm using the conversion factor.
Computes the median of the collected voltage and concentration readings.
Prints the median voltage and concentration values to the serial monitor.
Controls output pins based on the median concentration level:
<= 1700 ppm: Activates output on A1.
> 1700 ppm and <= 3400 ppm: Activates output on A2.
> 3400 ppm: Activates output on A3.
Median Calculation Function
Implements a simple bubble sort to arrange the array of readings.
Calculates and returns the median value from the sorted array.
Usage
Connect your analog sensor to pin A0 of the Arduino.
Connect any output devices to pins A1, A2, and A3.
Upload the sketch to your Arduino board.
Open the Serial Monitor to view median voltage and concentration readings.
Requirements
Arduino board (e.g., Uno, Nano)
Analog NaCl sensor
Appropriate wiring for your setup
