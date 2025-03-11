# Universal-Timer
Analog design and PCB project for an universal timer using Cadence OrCAD and PCB Editor

## Summary
This project focuses on developing a PCB layout for a universal timer, following a provided circuit diagram and specific parameters.

The timer includes:
- A **relay** that controls the activation and deactivation of the coil within the circuit
- A **potentiometer** for adjusting the operating time

Thanks to its electromagnetic relay, this compact circuit can be used in various applications. A few simple modifications allow for adjusting both the duration and the maximum operating interval.

The timing function is implemented using the LM555, a widely recognized component in the field. The Start (pin 2) and Stop (pin 4) inputs of the IC are normally held at a high voltage by resistors R4 and R6. In standby mode, the timing capacitor C2 is short-circuited to ground by the chip’s internal circuitry.

Once the **Start** button is pressed:
- The output (pin 3) switches to high, activating transistor T1, which in turn energizes the relay.
- To indicate activation, LED LD1 immediately lights up.
- Capacitor C2 begins charging through R1 and RV1.
- The delay before the output resets depends on C2 and RV1:

The higher the capacitance of C2 and the resistance of RV1, the longer the delay.
If the **Stop** button is pressed before the delay ends, the output is immediately deactivated, and C2 discharges.

The maximum delay period can be adjusted by modifying C2:
-Doubling the capacitance of C2 results in doubling the delay.
-Increasing RV1 also extends the delay, but for long durations, it may distort the scale due to reduced accuracy.

The selected relay can switch up to 2A at 230V. A stable 12V power supply is required for proper circuit operation.

## Files
