Motors, motor control, or anything related to motors.

STM32 Nucleo expansion boards - motor control selection guide: https://www.st.com/resource/en/brochure/stm32_nucleo_expansion_boards_motor_control_selection_guide.pdf

## Low voltage three phase and three sense motor driver
- [STSPIN233](https://www.st.com/content/ccc/resource/technical/document/datasheet/group3/9b/1c/56/b3/f5/43/4b/1c/DM00441037/files/DM00441037.pdf/jcr:content/translations/en.DM00441037.pdf)
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




