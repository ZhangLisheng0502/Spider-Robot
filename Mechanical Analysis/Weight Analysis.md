# Spider Robot – Weight Analysis

## 1. Objective

The objective of this analysis is to estimate the weight of the Spider robot's mechanical structure based on the current parts list.

The estimated weight will provide a basis for subsequent mechanical design, actuator selection and torque calculations.

## 2. Mechanical Component Weight

| Component | Quantity | Individual Weight (g) | Total Weight (g) |
|---|---:|---:|---:|
| Body | 1 | 30 | 30 |
| Coxa | 6 | 15 | 90 |
| Femur | 6 | 10 | 60 |
| Tibia | 6 | 5 | 30 |
| **Total** | **19** | | **210** |

## 3. Weight Distribution

The current estimated mechanical component weight is approximately 210 g.

The six legs account for most of the listed mechanical component weight. Each leg consists of a Coxa, Femur and Tibia.

The weight of each leg, excluding servos and fasteners, is estimated as:

15 + 10 + 5 = 30 g

Therefore, the total estimated weight of the six legs is:

6 × 30 = 180 g

## 4. Limitations

This estimate only includes the mechanical components listed in the current parts list.

The following components are not yet included:

- Servo motors
- Servo mounting brackets
- Screws and fasteners
- Battery
- Raspberry Pi
- Servo drivers
- Buck converter
- Wiring
- Additional structural components

Therefore, 210 g is not the total weight of the complete robot.

## 5. Next Steps

- Obtain the weight of individual servo motors.
- Estimate the weight of servo mounting structures and fasteners.
- Calculate the estimated total robot weight.
- Investigate the weight distribution of individual leg segments.
- Use the weight data for subsequent servo torque analysis.

## 3. Actuator and Electronic Component Weight

| Component | Quantity | Individual Weight (g) | Total Weight (g) |
|---|---:|---:|---:|
| MG90S Servo | 18 | TBD | TBD |
| Raspberry Pi Pico | 1 | TBD | TBD |
| PCA9685 Servo Driver | 2 | TBD | TBD |
| Battery | 1 | TBD | TBD |
| Buck Converter | 1 | TBD | TBD |
| Switch | 1 | TBD | TBD |

## 4. Estimated Total Robot Weight

| Category | Weight (g) |
|---|---:|
| Mechanical Structure | 210 |
| Actuators and Electronics | TBD |
| Estimated Total Weight | TBD |
