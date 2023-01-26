https://www.electricaltechnology.org/2020/08/soft-starter.html

## What is a soft starter:

- type of motor starter that uses the voltage reduction technique to reduce the voltage during the starting of the motor.
- offers gradual increase in voltage during motor startup allowing the motor to slowly accelerate & gain speed.
- Prevents mechanical tear & jerking due to sudden supplying of full voltage.
- The torque of an induction motor is directly proportional to the square of the current, which depends on the supply voltage. So the supply voltage can be used to control the starting torque. In a normal motor starter, applying full voltage to the motor generates maximum starting torque which possess mechanical hazard to the motor.
- Thus, a soft starter reduces starting torque & gradually increases it in a safe manner until it reaches its rated speed. At rated speed, the soft starter resumes the full voltage supply through it.
- During motor stopping, the supply voltage is gradually reduced to smoothly decelerate the motor. At zero speed, it breaks the input voltage supply to the motor.
- The main component used for the regulation of voltage in a soft starter is a Thyristor (SCR). Adjusting the firing angle of the thyristor regulates the voltage supplying through it. Other components such as OLR (overload relay) are used for overcurrent protection.


## Typical soft starter schematic:

![image](https://user-images.githubusercontent.com/42329930/214681899-c3a70d2c-d833-41d5-b00d-aa8b38bd4f82.png)


## Working Principle:
The main component used for controlling the voltage in a soft starter is a thyristor. It is a controlled rectifier that starts conduction of the current flow in only one direction when a gate pulse is applied called the firing pulse.

  ![image](https://user-images.githubusercontent.com/42329930/214682101-2eff1078-4a53-4452-bf2c-e12687295203.png)

The angle of the firing pulse determines how much of the input voltage cycle should be allowed through. Since AC swings between max & min, forming a complete 360° cycle, we can use the angle of firing pulse to switch on the thyristor for a specific duration and control the supplied voltage.

The firing pulses can vary between 0° to 180°. The decrease in the angle of firing pulse increases the conduction period of thyristor, thus allowing high voltage through it.

  ![image](https://user-images.githubusercontent.com/42329930/214682170-6bd9cb08-0e71-4d22-aaad-ee8d7d2f6aad.png)

Two such thyristors are connected in back-to-back formation for each phase. So it can control the current in both directions.

  ![image](https://user-images.githubusercontent.com/42329930/214682283-daea4ab8-897a-455d-8c9d-f2b90d755ab6.png)



## Circuit Explanation:
- The logic circuitry contains PID controller or a simple microcontroller programmed to generate pulses.
- When the motor starts up, the controller generates pulses for each individual SCR. The pulse is generated based on the zero crossing that is detected using a **zero crossing detector**. The first firing pulse angle is approximately near 180° (very low conduction period) to allow minimum voltage.
- Gradually after each zero crossing, the angle of firings pulses starts decreasing, increasing the conduction period of thyristor. The voltage through thyristor starts increasing. Hence the motor speed gradually increases.

- Once the motor attains its full rated speed (at 0° firing angle), the thyristors are completely bypassed using a bypass contactor. This increases efficiency since the SCRs stop firing. 
- During motor stopping, the SCR take control & starts firing in orderly fashion to reduce the supply voltage.


- The bypass contactors can be internal or external:
  - Internal bypass contactors are embedded inside the power switches. 
  - Each SCR have a bypass switch in parallel that supply the current under normal condition. Such contactor configuration takes small space & the starters are in compact design. 
  - External bypass contactors are connected externally in parallel with the soft starter. Such soft starter are bulky.
  - The bypass contactors are not meant to break or make the current supply to the circuit, thus can low rated contactors.




## Advantages
- Smooth Startup: gradual increase of voltage thus speed that results in smooth startup; leading to less mechanical stress or jerks that can damage the motor.
- Acceleration & Deceleration Control: 
- No Power Surges: the conventional motor starter allows full voltage across the motor resulting in a huge inrush current to the motor that can cause a -ve power surge in the circuit.
- Multiple Startups: Some applications require the motor to start/stop multiple times in small period of time. a motor without a starter will experience overheating due to high starting current.  
- Reduction of overheating: motor overheating occurs due to the high winding current during startup.
- Increased Life Span: reduces electrical & mechanical stress on the motor.
- Less Maintenance
- Increase efficiency.
- Compact & Small Size: The soft starter has a very compact design that takes up very small space. Unlike other motor starters, it has very small size.
- Low Cost: compared to other starters such as VFD, this is cheaper.

## Disadvantages
- No Speed regulation: The soft starter only allows the control of input voltage supply i.e. from 0 volts to line voltage with a fixed line frequency. Since the frequency is constant the motor speed is constant & only regulates by the load connected with it. The speed of induction motor is regulated by varying the supply frequency below or above the line frequency according to the need. Such feature is only available in VFD (variable frequency drive).
- Reduced starting Torque: Since it reduces the input voltage that corresponds to the input current which is directly proportional to the starting torque of the induction motor, it significantly reduces the starting torque. This is why Soft starters are used for low or medium starting torque application.


## Applications
- used for constant speed applications.
  - Fans: huge industrial fans usually run at constant speed. However, they do require the startup protection.
  - Conveyer belts: conveyer belts used for moving objects need care. Sudden jerks during start/stop using conventional starters may misalign and damages the belt and damage the objects placed on it.
- Motors using belt & pulleys: motor that drive loads through belts & pulleys cannot tolerate the sudden jerks. can cause wear/tear in the belt.
- Water or liquid pumps: such applications need smooth starting & stopping due to the sudden pressure building inside the pipes. 

