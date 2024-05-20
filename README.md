# PWM-kernel_module
A PWM (Pulse Width Modulation) kernel module in Linux is a piece of software that allows the kernel to interface with PWM hardware on the system. PWM is commonly used for controlling devices like LEDs, motors, and other peripherals where you need to vary the duty cycle to control the power delivered to the device. 

## Before starting PWM
 - Add this deve line in /boot/config.txt 
 - ``` dtoverlay=pwm-2chan,pin=12,func=4 ``` is used to enable and configure the PWM (Pulse Width Modulation) functionality on specific GPIO pins. 
 - ``` reboot now ```

## Lets start with pwm module 
 - We will work with pwm 0  GPIO 12 ![1_A2gpUDLyOx903dVUStHFTA](https://github.com/Rabie45/PWM-kernel-module/assets/76526170/e25d30b7-d5db-453c-8b7a-650a77f579d6)
 - - Move the module file and the Makefile to the raspberrypi
 - Install the headers for rasp kernel ```sudo apt install raspberrypi-kernel-headers```
 - ``` sudo scp Makefile pi@192.168.1.14:/home/pi```
 - ``` sudo scp hello.c pi@192.168.1.14:/home/pi```
 - Then go to raspbery pi and ``` make```
 - Them insert module to the kernel ```sudo insmod pwm.ko```
 - change the peremssion of the file created to the usersapce ```sudo chmod 777 /dev/test_file```
 - Default value the led will blink 50% on 50% off

https://github.com/Rabie45/PWM-kernel-module/assets/76526170/659d96ea-3ee5-44bb-9740-c7248f326533

 - To change the value 10% on 90% off ```echo 100 > /dev/test_file```

https://github.com/Rabie45/PWM-kernel-module/assets/76526170/de2c8897-6d3f-40bb-ac8f-deab483f1dbb

 - To change the value 90% on 10% off ```echo 900 > /dev/test_file ```
   
https://github.com/Rabie45/PWM-kernel-module/assets/76526170/3bf19218-ce6b-4976-b51b-1512d2890b24


