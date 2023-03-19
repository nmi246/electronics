

## Connectivity ----------------------------------
### ULP-UART



### CAN-FD




## Math Accelerators ------------------------------
#### CORDIC (COordinate Rotation DIgital Computer)
- https://www.st.com/resource/en/product_training/STM32G4-Peripheral-Cordic_Coprocessor_CORDIC.pdf
- The CORDIC co-processor provides hardware acceleration of certain mathematical functions, notably trigonometric, commonly used in motor control, metering, signal processing and many other applications
- The Cordic block is an AHB slave that inserts wait state when the MCU requests the result until the operation is completed. No input/output driver is therefore needed.
- Another approach consists in enabling the Cortex-M4 to handle other processing while the Cordic calculation is in progress. In this case an interrupt request indicates that the result is available.
- DMA channels can be implemented to provide the arguments from memory and to write the result to memory.
- The Cordic block supports a pipelined operation: next arguments can be provided while the calculation with the current arguments is in progress.
- Note that the Cordic block is a fixed-point arithmetic accelerator.
- CORDIC is a hardware-efficient iterative method which uses rotations to calculate a wide range of elementary functions.
- In trig (circular) mode, the sine and cosine of an angle θ are determined by rotating the unit vector [1, 0] through decreasing angles until the cumulative sum of the rotation angles equals the input angle.
- The x and y Cartesian components of the rotated vector then correspond respectively to the cosine and sine of θ.
- Inversely, the angle of a vector [x, y], corresponding to arctangent (y/x), is determined by rotating [x, y] through successively decreasing angles to obtain the unit vector [1, 0].
- The cumulative sum of the rotation angles gives the angle of the original vector.
- The CORDIC algorithm can also be used for calculating hyperbolic functions (sinh, cosh,atanh) by replacing the successive circular rotations by steps along a hyperbola.

![image](https://user-images.githubusercontent.com/42329930/226210394-061ec942-4043-4420-a0a7-a6965499161c.png)
  
  
  
  
#### FMAC (Filter Math ACcelerator)
https://www.st.com/resource/en/product_training/STM32G4-Peripheral-Filter_Math_Accelerator_FMAC.pdf
- The FMAC unit is built around a fixed point multiplier and accumulator (MAC).
- The MAC units receives two fixed-point 16-bit operands from an internal 256x16-bit RAM and write the result back to this memory.
- The address of the input values in local memory is determined using a set of pointers.
- These pointers can be loaded, incremented, decremented or reset by the internal hardware.
- Software does not access them directly. The unit allows frequent or lengthy filtering operations to be offloaded from the CPU, freeing up the processor for other tasks.

- ![image](https://user-images.githubusercontent.com/42329930/226210667-fbc5a00b-0210-4903-aeef-91be85b154b6.png)
Features:
- ![image](https://user-images.githubusercontent.com/42329930/226210692-cff2e822-db19-4ee9-acfc-751bf888113a.png)
















