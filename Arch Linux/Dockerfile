FROM base/archlinux

COPY esp-open-sdk-1.4.0-2-x86_64.pkg.tar.xz /tmp/esp-open-sdk-1.4.0-2-x86_64.pkg.tar.xz
COPY gcc-arm-none-eabi-bin-7_2017_q4_major-1-x86_64.pkg.tar.xz /tmp/gcc-arm-none-eabi-bin-7_2017_q4_major-1-x86_64.pkg.tar.xz
#COPY gcc-xtensa-esp32-elf-bin-1.22.0_80_g6c4433a_5.2.0-1-x86_64.pkg.tar.xz /tmp/gcc-xtensa-esp32-elf-bin-1.22.0_80_g6c4433a_5.2.0-1-x86_64.pkg.tar.xz

RUN pacman -Syu --noconfirm python python2 python-pyserial python2-pyserial
RUN pacman -U --noconfirm /tmp/esp-open-sdk-1.4.0-2-x86_64.pkg.tar.xz

RUN pacman -U --noconfirm /tmp/gcc-arm-none-eabi-bin-7_2017_q4_major-1-x86_64.pkg.tar.xz

RUN pacman -Syu --noconfirm avr-libc

RUN pacman -Syu --noconfirm git make

RUN useradd -m tester

WORKDIR /home/tester

USER tester

RUN git clone https://github.com/MayaPosch/Nodate.git  /home/tester/Nodate

ENV NODATE_HOME=/home/tester/Nodate

RUN echo "export PATH=$PATH:/opt/esp-open-sdk/xtensa-lx106-elf/bin/" >> /home/tester/.bashrc


