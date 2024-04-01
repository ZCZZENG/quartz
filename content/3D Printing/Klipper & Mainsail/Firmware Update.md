# Compiling the new Firmware
After updating Mainsail & Dependencies to the newest versions, ssh into the cb1.

run 
```sh
cd ~/klipper/
make menuconfig
```

check this option
```
[*] Enable extra low-level configuration options
```

exit with q and run the command
```
make
```

# Flashing the firmware
First of all, we need to get the klipper.bin file.

FTP into our cb1.
Navigate to `~/klipper/out` and copy it locally.

Rename the file to `firmware.bin`, put it on a SD Card.
Put the SD Card in the Board, turn it on.

>[!note]
>Depending on your type of Board, there are different SD Card slots. 
>On the Manta M4P there is a big SD Card Slot (used for flashing) and a micro SD Card slot (used for software)
