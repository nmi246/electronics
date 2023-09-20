source: https://www.ti.com/lit/an/slvae59a/slvae59a.pdf?ts=1695032876681&ref_url=https%253A%252F%252Fwww.google.com.hk%252F


## Types of Solenoids
There are three main categories of solenoids; push/pull, latching/bistable, and proportional.
The first type, push/pull or monostable, is used to displace an object by energizing and de-energizing the coil,
or where "in and out" movement is needed. Push/pull solenoid is made up of an iron frame, iron plunger, copper
coil, and return spring. Figure 1-1 shows a cross-sectional view of a pull-type solenoid. This type of solenoid can
be found in applications such as electronic door locks, valves, and robotics.

![image](https://github.com/nmi246/electronics/assets/42329930/a83af40e-a32d-4b93-ae17-9570f205477d)

The second type is the latching/bistable solenoid. The latching/bistable is similar in use to the push/pull, but
the latching solenoid can maintain its position after power is off. When off, the position of latching solenoid is
maintained by a permanent magnet, as opposed to a spring for push/pull solenoid. Energizing the coil with a
pulse of current will change the position of the solenoid.

Proportional solenoids are solenoids that generate a force proportional to the current flowing through it, as
opposed to solenoids changing between two positions or states. By adding a spring, the solenoid can generate
a displacement which is proportional to current. In applications such as hydraulics, these solenoids can also
be constructed with an air gap, so that fluid pressure does not affect force characteristics of the solenoid. This
allows for very fine force and positioning control.


## Solenoid Driving Typologies
Most systems today use motor drivers to actuate and de-actuate solenoid. The key to driving a solenoid is which
FETs to switch on and off, and when to switch them.
There are three basic driver configurations, low-side, high-side, and half-bridge/full-bridge, each with their tradeoffs. Choosing which configuration depends on the system requirements, such as switching speed and fault
protection. The high-side driver can protect against short to ground fault, whereas a low-side driver protects
against short to battery fault.

![image](https://github.com/nmi246/electronics/assets/42329930/ba2a3c07-e81c-43ab-b0c4-5fad120a3af9)


## Basics of Driving Solenoid Loads
Because solenoids are inductive loads, they store energy in the magnetic field when current flows through the
coil. Whether disabling the solenoid or using PWM to maintain a specific current level, any circuitry used to
drive a solenoid must never abruptly stop the flow of current. Doing so will cause a large voltage spike due to
the energy leaving the solenoid. This is apparent from the expression that defines the voltage characteristic of
inductors: V = L*di/dt.

As mentioned in the previous sections, freewheeling diodes allow for the current to recirculate when the driving
FET disables. This keeps the voltage across the solenoid equal to the forward voltage drop of the diode. When
disabling a solenoid, the current will recirculate until the energy stored in the inductor dissipates as heat in the
series resistances of the diode and solenoid. Because the current decreases slowly, freewheeling diodes should
be used in systems when PWM or current regulation schemes are used to implement peak and hold control for
power savings.

Some circuits require solenoids to disable quickly to minimize latency in the system for valves or actuators.
Clamping circuits may be integrated into the driver or added externally to help dissipate the energy. For instance,
adding a Zener diode in series with the freewheeling diode will help to dissipate energy quickly from the
solenoid. In this case, the voltage drop across the solenoid when the driving FET is disabled will be equal to the
Zener clamping voltage plus the diode drop. Because this voltage is much higher than the freewheeling diode
alone, it will dissipate the stored inductive energy much fast.

## Current Control
Driving solenoids with current control requires two things: current sense and current regulation. The advantages
of current control are improved efficiency and reliability across temperature. As the solenoid or relay coil heats
up from I2R losses or is warmed by its environment, the coil resistance increases. With the current-sense
feedback, the current can be monitored and adjusted to produce a constant force even with the changes in
resistance.

The second advantage is that it can provide some measure of protection from higher than rated supply voltage.
Solenoids have voltage ratings because they can be destroyed by too much current going through the coil, which
happens when driving at higher voltages. This problem can be managed with current-sense feedback, and by
controlling the current going through the solenoid regardless of the supply voltage. This allows a single solenoid
driver design to be reused on multiple products.

There are two methods for providing load current feedback from motor driver IC to a microcontroller. One
method is from a current shunt amplifier using an external sense resistor that is connected either in line with the
load, or on the high- or low-side. The other is from a current mirror, which provides a proportional current to load
current to pin output, removing the need for an external sense resistor. This proportional current output method
is available for motor driver ICs with integrated MOSFETs. One limitation here is that generally, both high- and
low-side sense output may not always be available for a given integrated motor driver IC.
To regulate current and energize and de-energize most solenoids, peak-and-hold drive is desired. Figure 3-1
below shows an example of this expected peak-and-hold current.

![image](https://github.com/nmi246/electronics/assets/42329930/bba0e2a4-6052-4421-8def-d5978bf29420)

The charging current is drawn or driven into the solenoid, called the peak current. The current in the solenoid
will ramp to its peak, at which point the magnetic field will depress the plunger into the spring. To maintain
the solenoid in this position, current must still be drawn or driven into the solenoid. This is referred to as hold
current. However, this current is far lower than the peak current. To further minimize power dissipation through
the solenoid during hold phase, the hold current can be regulated.
Just as pulse width modulation (PWM) is used to drive other types of motors, it also can be used to drive
solenoids. PWM can be used to regulate the current of a solenoid to different levels at different times by varying
the duty cycle. This allows the user drive a longer or maximum duty cycle to pull in the solenoid, and then
a shorter duty cycle to hold it in place, optimizing the power consumption. Figure 3-2 shows the current and
voltage driving outputs for the PWM implementation.

![image](https://github.com/nmi246/electronics/assets/42329930/f03eedb1-fa5e-40dd-92ed-f7f02afb36d9)


This reduces power consumption of the solenoid solution, due to the lower current in the coil. If the drive current
is not reduced, power dissipation will heat up the solenoid further. With the increase in temperature the solenoid
initial resistance will also increase, all of which can lead to unintentional de-actuation or failing to actuate the
solenoid. Note in the above screenshot that the drop-out or de-actuation time is roughly 10 ms.





