# Vireo for Microprocessors

This is a project for getting [Vireo](https://github.com/ni/VireoSDK), a runtime engine for VIs saved in VI assembly (.via) format, compiled and running on microprocessor targets like Raspberry Pi Pico (RP2040).

## Goal: User Experience Similar to MicroPython/CircuitPython

A great installation and user experience solution would be something similar to MicroPython/CircuitPython (see [Installing CircuitPython](https://learn.adafruit.com/welcome-to-circuitpython/installing-circuitpython) and [The CircuitPy Drive](https://learn.adafruit.com/welcome-to-circuitpython/the-circuitpy-drive)).

### Installing Vireo onto a Microprocessor Board

*   When a board doesn't have any firmware (or is loaded into the bootloader by holding down the bootloader button at startup) it shows as a USB drive named "PICO" (for the Raspberry Pi Pico).
*   The user can copy the Vireo binary (a uf2 file) to the "PICO" USB drive, to install Vireo.
*   After copying the file, the board will reset and load the Vireo firmware.

### Running a VI Assembly (.via) File

*   With the Vireo firmware running, the board will show up as a "VIREO" USB drive on the user's computer.
*   The user then copies over a `main.via` file, which causes the Vireo firmware to immediately run it (or restart it when the `main.via` file is re-saved).  Vireo also runs this `main.via` file at boot/startup if present.
