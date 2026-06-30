hi! 

Welcome to the repo for SimPad, my custom flight simulator controller. I got tired of using my keyboard for everything, so I decided to design and build my own hardware to make flying a lot more immersive.

# Why SimPad?

As an aspiring mechanical engineer with a focus on automotive (cars) and aerospace (planes and rockets), with a slight more interest in the latter, I wanted to build something that would include the mechanics of controlling a plane or a car. GeoFS has always captivated me, but I often found it irritating to use a keyboard and mouse, constantly reaching for the buttons; this frustration led me to the idea of creating a solution that allows us to feel the cockpit at home :)

# How it Works

The Hardware Brain: It uses an STM32 microcontroller, a USB-C port to gain voltage from the computer, a voltage booster, 7 tactical switches, 3 rotary encoders, 1 rotary switch, and one metal toggle. So basically the STM32 uses the USB-C's VBUS-A pad to receive the input voltage of 5V, which is then used to power all of the switches connected to random empty pads on the microcontroller; moreover, the buck converter takes the higher input voltage (5V) and efficiently steps it down to the stable 3.3V required to power your microcontroller and other components. The STM32 is constantly monitoring the status of your various inputs—switches (S1, S2, S3), push buttons (SW9–SW13), and encoders (SW1, SW2, SW3); When you flip a switch, the STM32 detects a voltage change on one of its pins where it runs the firmware to determine what this switch actually does in the context of a flight sim. 

Comms:  The STM32 communicates with your PC via the USB-C connector, through the D+/D- differential data lines; it tells the flight simulator, "Hey, this switch has been flipped!"

Filtering: Capacitors ($C1, C2$) are placed to smooth out voltage noise for stable USB communication.

# PCB and Schemantics

<img width="1277" height="901" alt="image" src="https://github.com/user-attachments/assets/c7a3252a-fb59-4215-8592-eee60b34b244" />

<img width="802" height="646" alt="image" src="https://github.com/user-attachments/assets/1a5986e8-b059-414c-a8c6-23535ac0bcd6" />

# 3D View of PCB

<img width="1067" height="762" alt="image" src="https://github.com/user-attachments/assets/7532cecd-a96d-4241-98b0-d38566e0f378" />

<img width="1102" height="657" alt="image" src="https://github.com/user-attachments/assets/048c40f7-b0cc-48c8-a766-2f9e8e06dc34" />

# 3D enclosure of the PCB

<img width="1375" height="736" alt="Screenshot 2026-06-29 123144" src="https://github.com/user-attachments/assets/ee10eb24-4f3f-4bdf-99bc-d067eaca29b6" />










