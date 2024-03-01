# BBB-AD4630
Code to run on a Beaglebone to collect data from the AD4630-24

This repository contains code to do the following - 
- Configure PRU0 to count pulses from the reference clock and generate the CNV pulse a specified number of times as commanded by the ARM core
- Configure PRU1 to collect data each time BUSY goes low and store it in a buffer allocated by the ARM core
- ARM core allocates memory, triggers PRU0/1 over over RPMsg, calculates the FFT and visualizes it in a web UI