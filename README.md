battery managment system based on the BQ76940 from Texus Instruments

This project supports akkupacks from 9 to 15 serial Li-Ion based cells (max. Voltage ~63 Volt). It can balance each cell and turns the charge and discharge MOSFETs to control the system over i2c.

Measuring:

- up to 15 cell voltages
- akkupack voltage
- tempreature (internal + external)
- akkupack current

Protection:

- overcurrent in discharge
- overcurrent in discharge
- overvoltage
- undervoltage

My System

For the dokumentation see /Dokumentation/DA_HM_15.pdf where you can find my hole work (german). The important BMS part is shown in capter 5.

The realized system has the following specifications:

- µC: ATmega168PA
- programming was done in C with Linux in nano and the AVR-Tools (avr-gcc, avr-objcopy, make)
- to programm the µC i use avrdude over USB
- the current system is based on 15 cells and max. 60 Volts
- balancing and loading the akkupack
- balancingcurrent up to ~105 mA
- 3x temp. sensors
- switches current up to ~70 Ampere

All testing and programming was done with the developed EvalBoard. For schematica and layouts see /kicad (http://kicad-pcb.org/).

For testing the given example run the Makefile (in /example): (boot the BQ76940 with 3.3V on TS1) (bootet if 3.3V on REGOUT/3V3_init)

    make clean
    make all
    sudo make load

ToDO:

testing heating distribution under use
testing current measuring funktion

License Information

This code is public domain to support electromobility and is a collaboration between Nathan Seidle (https://github.com/nseidle/BMS) and me.
