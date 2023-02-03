# CPU/MPU products and schematics on how to use them. 

  
    
    
      
     
# STM32MP151A Circuit Diagram:
![image](https://user-images.githubusercontent.com/42329930/216506631-953b2746-484c-4b48-a26a-fe61f80eb8b6.png)
- webpage + datasheet: https://www.st.com/en/microcontrollers-microprocessors/stm32mp151a.html

# Parts description:

## Processing Units:
- MPU: ARM Cortex-A7 - 800 MHz (with 2x internal L1 cache, 1x internal L2 cache) 
  - contain
  - runs openSTlinux distribution
- MCU: ARM Cortex-M4 - 209 MHz (FPU + MPU)
  - for real time functionality 
  -


## Internal Memories
- system RAM 256 kB
- MCU system RAM
- backup RAM
- MCU retention RAM 
- OTP fuse

## External Memories
- DDR3/DDR3L/LPDDR2/LPDDR3 32 bit at 533 MHz
- SDMMC
- Dual quad SPI
- 16 bit SLC NAND 8-bit ECC

## Connectivity
- ETH
- USB
- Camera interface
- HDMI-CEC
- MDIO Slave
- DFSDM
- SPI
- I2S
- UART / USART
- [SAI (serial audio interface)](https://www.st.com/content/ccc/resource/training/technical/product_training/group0/d3/c0/b0/0e/fe/eb/40/a9/STM32H7-Peripheral-Serial-Audio-Interface_SAI/files/STM32H7-Peripheral-Serial-Audio-Interface_SAI.pdf/_jcr_content/translations/en.STM32H7-Peripheral-Serial-Audio-Interface_SAI.pdf)
  - The SAI integrated inside STM32 products provides an interface allowing the microcontroller to communicate with external audio devices such as amplifiers, ADCs, DACs or audio processors. This interface is fully configurable and supports most audio standards, allowing easy connection to existing audio devices.
  - support various standards: I2S, TDM, SPDIF
  - digital microphone interface
  - supports several protocols:
    - Free protocol modes: 
      - I2S (inter-IC sound - Phillips stadard)
      - I2S MSB or LSB justified
      - TDM (time division multiplexing)
      - PCM (pulse code modulation)
    - SPDIF output (sony/phillips digital interface)
    - PDM interface (pulse density modulation)
    - AC'97 interface (Audio codec 97 from intel) 
- 

## Control
- 16 bit Advanced motor control timers
- 16 bit timers
- 32 bit timers
- 

## Analog
- 16-bit ADC
- 12 bit DAC

## System
- LDO
- internal / external oscillator
- MDMA + DMA
- Reset and clock
- watchdog
- 

## Graphics
- [LCD TFT controller](https://www.st.com/resource/en/application_note/an4861-lcdtft-display-controller-ltdc-on-stm32-mcus-stmicroelectronics.pdf)
  -

## Security
- AES 256, TDES
- Secure Boot
- Secure RTC







