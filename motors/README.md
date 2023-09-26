# TI Precision Labs courses on motors:
- [Introduction to motor drivers](https://www.ti.com/video/series/precision-labs/ti-precision-labs-introduction-to-motor-drivers.html)
- [Brushed-DC motors](https://www.ti.com/video/series/precision-labs/ti-precision-labs-brushed-dc-motors.html)
- [Stepper motors](https://www.ti.com/video/series/precision-labs/ti-precision-labs-stepper-motors.html)
- [Brushless-DC motors](https://www.ti.com/video/series/precision-labs/ti-precision-labs-brushless-dc-motors.html)
- [Motor technology](https://www.ti.com/video/series/precision-labs/ti-precision-labs-motor-technology.html)
- [Designing with motor drivers](https://www.ti.com/video/series/precision-labs/ti-precision-labs-designing-with-motor-drivers.html)


# Motors, motor control, or anything related to motors.

STM32 Nucleo expansion boards - motor control selection guide: https://www.st.com/resource/en/brochure/stm32_nucleo_expansion_boards_motor_control_selection_guide.pdf

## Low voltage three phase and three sense motor driver
- [STSPIN233, from STMicro, $3.06USD ea from Digikey](https://www.st.com/content/ccc/resource/technical/document/datasheet/group3/9b/1c/56/b3/f5/43/4b/1c/DM00441037/files/DM00441037.pdf/jcr:content/translations/en.DM00441037.pdf)
- Digikey: https://www.digikey.com/en/products/detail/stmicroelectronics/STSPIN233/8346481
- Operating voltage 1.8-10V, I_out max 1.3Arms, RDS(on) HS + LS = 0.4Ω typ, Supporting three shunt sensing topology
– Non-dissipative overcurrent protection, short-circuit protection, thermal shutdown
- Direct driving, dedicated input and enable pin for each half-bridge
- Half Bridge (3) Driver DC Motors, General Purpose Power MOSFET 16-VFQFPN (3x3)
- Battery powered 3-phase BLDC motors in applications such as:
  - drones and portable gimbals
  – Portable health care products, and medical equipment
  – Low voltage electronic valves
  – Toys, Robotics
![image](https://user-images.githubusercontent.com/42329930/218914634-8f2b0159-5ca8-4e90-86a2-ec5a9bbdb5fc.png)
![image](https://user-images.githubusercontent.com/42329930/218915133-2b77a8e5-d5da-41d7-901a-c704d62b6e2d.png)



## Stepper motor:
- wikipedia: https://en.wikipedia.org/wiki/Stepper_motor
- stepper motor driver + driver waveforms: 
  - https://blog.poscope.com/stepper-motor-driver/
  - https://www.youtube.com/watch?v=9ECnh0UOr6g&list=PLgSpn2wTDbU-hYNIvC72Bzp6XcKKeT-09&index=2&t=584s&ab_channel=welcomehelloJ
- how stepper motor works: https://www.youtube.com/watch?v=eyqwLiowZiU&list=PLgSpn2wTDbU-hYNIvC72Bzp6XcKKeT-09&index=8
- Arduino and Stepper Motor Configurations: https://docs.arduino.cc/learn/electronics/stepper-motors
