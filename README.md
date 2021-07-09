# Vireo for Microprocessors

This is a project for getting [Vireo](https://github.com/ni/VireoSDK), a runtime engine for LabVIEW VIs saved in VI assembly (.via) format, compiled and running on microprocessor targets like Raspberry Pi Pico (RP2040).

## Short Term Goal: "Hello World!" on the RPI Pico

Our "Hello World!" proof of concept will basically look as follows:

*   **Build Vireo for RPI Pico** - Build Vireo into an RF2 file that can be run on the RPI Pico
*   **Start Vireo in Interactive Mode** - Have Vireo start in interactive mode (where it is listening for commands on STDIN and outputting print statement results to STDOUT)
*   **Use USB Serial for STDIO** - Use the Pico's USB serial UART for STDIN and STDOUT, so that VIA commands and results can be sent via serial.
*   **Send "HelloWorld.vi" via Putty** -  Use Putty (or Minicom) to send the  "HelloWorld.via" VIA data to Vireo and view the response.

Alternatively, it might be easier to not start Vireo in interactive mode and simply build "HelloWorld.via" into the RF2 file and execute it at startup. 

## Longer Term Goal: User Experience Similar to MicroPython/CircuitPython

A great installation and user experience solution would be something similar to [MicroPython](https://github.com/micropython/micropython)/[CircuitPython](https://github.com/adafruit/circuitpython) (see [Installing CircuitPython](https://learn.adafruit.com/welcome-to-circuitpython/installing-circuitpython) and [The CircuitPy Drive](https://learn.adafruit.com/welcome-to-circuitpython/the-circuitpy-drive)).

### Installing Vireo onto a Microprocessor Board

*   When a board doesn't have any firmware (or is loaded into the bootloader by holding down the bootloader button at startup) it shows as a USB drive named "PICO" (for the Raspberry Pi Pico).
*   The user can copy the Vireo binary (a uf2 file) to the "PICO" USB drive, to install Vireo.
*   After copying the file, the board will reset and load the Vireo firmware.

### Running a VI Assembly (.via) File

*   With the Vireo firmware running, the board will show up as a "VIREO" USB drive on the user's computer.
*   The user then copies over a `main.via` file, which causes the Vireo firmware to immediately run it (or restart it when the `main.via` file is re-saved).  Vireo also runs this `main.via` file at boot/startup if present.

## Idea: Could some of MicroPython/CircuitPython sources be leveraged for Startup and GPIO 

The [MicroPython](https://github.com/micropython/micropython) and [CircuitPython](https://github.com/adafruit/circuitpython) projects have already solved the challenge of abstracting the handling of Startup and GPIO. Could that codebase be leveraged and linked to the vireo runtime instead of python?

## Want to Help?

*   [Join the discussion here](https://github.com/labview-for-microcontrollers/exploring-labview-for-microcontrollers/discussions).
