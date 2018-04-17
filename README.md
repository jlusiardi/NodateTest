# Test environments for Nodate # 

This project should provide environments to compile and test Nodate on different distributions.

## Build the Docker container ##

Use the following command to build the environment:

`docker build -t nodatatest_${DISTRIBUTION} ${DISTRIBUTION_DIR}/` 


## Test within container ##

To start a container for tests:
`docker run --rm -ti nodatatest_${DISTRIBUTION}:latest`

This opens a shell. Go `/home/tester/Nodate/examples/blinky` (or any other example) and execute one of the following commands:

 * `ARCH=avr MCU=atmega2560 BOARD=arduino_mega_2560 make` for AVR atmega2560
 * `ARCH=esp8266 MCU=esp8266 VARIANT=d1_mini make` for esp8266 on d1 mini
 * `ARCH=sam BOARD=arduino_due VARIANT=arduino_due_x make`
