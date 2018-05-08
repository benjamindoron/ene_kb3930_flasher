Ene KB3930 Flasher is a tool that uses the EC Index LPC I/O to communicate with the EC in order to dump or flash the EC SPI flash ROM from software.

Build:

Type `make`

Dumping the flash :

`./ene_kb3930_flasher -r dump.rom`

Flashing a new EC image :

`./ene_kb3930_flasher -w image.rom`

Flashing a new EC image will cause the EC to be reset which will prevent any interaction with the computer (since the PS/2 keyboard and mouse are handled by the EC), and once the write operation is finished, the EC is reset which will cause the computer to forcibly shutdown (since the EC takes care of the power-on sequence, once the EC is reset, it will restart the power sequence, as if the computer had just had its battery inserted)

It is therefore recommended to write the EC from a live USB or a boot mode specifically made for it to avoid corrupting your partitions when the computer shuts down. Otherwise, at least make sure you save all your work and have no open application that might be writing to the disc.
