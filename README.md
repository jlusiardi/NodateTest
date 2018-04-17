# Test environments for Nodate # 

This project should provide environments to compile and test Nodate on different distributions.

## Build the Docker container ##

Use the following command to build the environment:

`docker build -t nodatatest_${DISTRIBUTION} ${DISTRIBUTION_DIR}/` 


## Test within container ##

To start a container for tests:
`docker run --rm -ti nodatatest_arch:latest`

This opens a shell. Go `/home/tester/Nodate/examples/blinky` (or any other example) and execute one of the following commands:

 * `make` for AVR atmega2560
 * `ARCH=esp8266 MCU=esp8266 make` 
 * `ARCH=sam BOARD=arduino_due make`
