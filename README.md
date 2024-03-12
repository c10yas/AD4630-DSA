# AD4630-DSA

This project consists of 3 parts
- hw/
  - PCB files for the main board that contains the ADC, power supplies, isolators, and connection points to the Beaglebone Black
- sw/
  - pru/
    - PRU code that runs on the BBB, generating the correct control signals and reading the data into DRAM
  - arm/
    - ARM code to save data to file, generate real-time FFTs, etc, and host a web interface to control the whole system

Code to run on a Beaglebone to collect data from the AD4630-24

This repository contains code to do the following - 
- Configure PRU0 to count pulses from the reference clock and generate the CNV pulse a specified number of times as commanded by the ARM core
- Configure PRU1 to collect data each time BUSY goes low and store it in a buffer allocated by the ARM core
- ARM core allocates memory, triggers PRU0/1 over over RPMsg, calculates the FFT and visualizes it in a web UI
