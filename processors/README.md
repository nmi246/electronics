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
- [MDIO Slave](https://www.st.com/resource/en/product_training/STM32F7_Peripheral_MDIOS.pdf)
  - management data input/output slave controller; used to exchange management data with a host device.
  - 
- DFSDM
- SPI

- [I2S](https://www.st.com/resource/en/application_note/an4309-interfacing-an-stm32l1xx-microcontroller-with-an-external-i2s-audio-codec-to-play-audio-files-stmicroelectronics.pdf)
  - 


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
  - MDMA: master direct memory access controller 
  - DMA: direct memory access controller
- Reset and clock
- watchdog
- 

## Graphics
- [LCD TFT controller](https://www.st.com/resource/en/application_note/an4861-lcdtft-display-controller-ltdc-on-stm32-mcus-stmicroelectronics.pdf)
  - TFT LCD: Thin film transistor Liquid crystal display
  - The MCU computes the image to be displayed in the framebuffer, assembling graphical
primitives such as icons or images. The CPU performs this operation by running a
graphical library software. This process can be accelerated by a dedicated hardware
like the DMA2D Chrom-Art Accelerator, used by the graphical library. The more often
the framebuffer is updated, the more fluent the animations are (animation fps)
  - The framebuffer is a volatile memory used to store pixel data of the image to be
displayed. This memory is usually called the graphic RAM (GRAM). The required size
of the framebuffer depends on the resolution and color depth of the display. 
Double buffering is a technique that uses double framebuffers to avoid displaying what
is being written to the framebuffer.
  - The display controller is continuously “refreshing” the display, transferring the
framebuffer content to the display glass 60 times per second (60 Hz). The display
controller can be embedded either in the display module or in the MCU.
The display glass is driven by the display controller and is responsible to display the
image that is composed of a matrix of pixels.
  - A display is characterized by:
    – Display size (resolution): defined by the number of pixels of the display, represented by horizontal (pixels number) x vertical (lines number).
    – Color depth: defines the number of colors in which a pixel can be drawn, represented in bits per pixel (bpp). For a color depth of 24 bpp (that can also be
represented by RGB888) a pixel can be represented in 16777216 colors.
    – Refresh rate (in Hz): number of times per sec that the display panel is refreshed.

Basic embedded graphic system: 
- A basic embedded graphic system is composed of a microcontroller, a framebuffer, a display controller and a display glass.
![image](https://user-images.githubusercontent.com/42329930/216523278-c4c812b3-aced-4081-9bac-957336260c0c.png)


## Security
- AES 256, TDES
- Secure Boot
- Secure RTC







