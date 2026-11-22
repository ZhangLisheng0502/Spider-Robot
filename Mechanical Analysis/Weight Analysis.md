# Weight Analysis

## 1. Objective

The objective of this preliminary weight analysis is to estimate the total mass of the Spider robot and understand the contribution of its mechanical structure, actuators and electronic components.

This analysis provides an initial reference for mechanical design, mass distribution considerations and future actuator torque calculations.

At the current stage, some component weights are estimated rather than measured. Therefore, the calculated total mass should be treated as a preliminary estimate and updated as the mechanical design develops.

---

## 2. Mechanical Component Weight

The mechanical structure consists of the main body and six sets of leg components.

| Component | Quantity | Individual Weight (g) | Total Weight (g) |
|---|---:|---:|---:|
| Body | 1 | 30 | 30 |
| Coxa | 6 | 15 | 90 |
| Femur | 6 | 10 | 60 |
| Tibia | 6 | 5 | 30 |
| **Mechanical Structure Total** | | | **210** |

The current estimated mechanical structure weight is:

**210 g**

These values are preliminary estimates and may change depending on the final design, material selection, manufacturing method and structural optimisation.

The mechanical structure weight does not represent the total robot weight, as actuators, electronics, wiring, mounting hardware and other components must also be included.

---

## 3. Weight Distribution

Weight distribution is an important consideration in the mechanical design of a hexapod robot.

The position of each component affects the overall centre of mass and the gravitational loading experienced by individual leg joints.

Components located farther away from a joint generally contribute a greater gravitational moment because of their longer lever arms.

The following considerations will be important during the future design stage:

- The distribution of mass between the robot body and the six legs.
- The position of the servos relative to their respective joints.
- The mass of distal leg components.
- The centre of mass of each leg segment.
- The overall centre of mass of the robot.
- The effect of component placement on balance and stability.

The current weight analysis only provides a preliminary estimate of total component mass. A detailed mass distribution analysis will be conducted once the mechanical geometry and component positions have been established.

---

## 4. Limitations

The current mechanical weight estimates are preliminary and have not yet been verified through final CAD mass properties or physical weighing.

The final mechanical structure may differ from the current estimates due to:

- Changes in component dimensions.
- Material selection.
- Manufacturing methods.
- Structural reinforcement requirements.
- Mechanical optimisation.
- Mounting brackets and fasteners.

The estimated mechanical weight of 210 g should therefore not be treated as the final weight of the complete mechanical structure.

Additional components such as screws, nuts, servo mounting brackets, wiring and other mounting hardware may increase the final weight.

---

## 5. Actuator and Electronic Component Weight

The Spider robot requires actuators, electronic control components and a power supply system.

The following table provides a preliminary estimate of their mass.

| Component | Quantity | Individual Weight (g) | Total Weight (g) |
|---|---:|---:|---:|
| MG90S Servo | 18 required | 13.4 (estimated) | 241.2 |
| Raspberry Pi Pico | 1 | 3 (estimated) | 3 |
| PCA9685 Servo Driver | 2 | 9 (estimated) | 18 |
| Battery (7.4V, 2S, 4000mAh) | 1 | 100 (estimated) | 100 |
| Buck Converter | 1 | 12 (estimated) | 12 |
| Switch (ZF DB3C-A1LB) | 1 | 2 (estimated) | 2 |
| **Actuators and Electronics Total** | | | **376.2** |

### 5.1 MG90S Servos

The Spider robot requires 18 MG90S servos.

A preliminary individual servo weight of 13.4 g is assumed.

Total servo weight:

18 × 13.4 = 241.2 g

Therefore, the estimated total mass of the required servos is:

**241.2 g**

The project currently has 20 servos available, while 18 are required for the robot.

The estimated servo weight should be verified against the actual servo specification or physical measurements. Servo weight may vary depending on the exact version and whether accessories such as servo horns and mounting screws are included.

### 5.2 Raspberry Pi Pico

The Raspberry Pi Pico is used as the robot's microcontroller.

A preliminary weight of approximately 3 g is assumed for the weight calculation.

This value should be verified against the actual board and any additional headers or mounting hardware.

### 5.3 PCA9685 Servo Drivers

Two PCA9685 servo driver boards are included in the current hardware configuration.

An estimated individual board weight of 9 g is assumed.

Total estimated weight:

2 × 9 = 18 g

The actual weight may vary depending on the board design, connector configuration and additional mounting hardware.

### 5.4 Battery

The selected battery is:

- Voltage: 7.4 V
- Configuration: 2S
- Capacity: 4000 mAh

A preliminary battery weight of approximately 100 g is assumed.

The actual weight should be verified using the battery specification or physical measurement, as battery mass may vary depending on its manufacturer, dimensions and packaging.

### 5.5 Buck Converter

One buck converter is included in the current hardware configuration.

A preliminary weight of approximately 12 g is assumed.

The exact weight has not yet been verified against the final converter model.

### 5.6 Switch

The selected switch is:

ZF DB3C-A1LB

A preliminary weight of approximately 2 g is assumed.

The exact weight should be confirmed using the component specification or physical measurement.

---

## 6. Estimated Total Robot Weight

The preliminary total robot weight is calculated by combining the estimated mechanical structure weight with the actuator and electronic component weight.

### Mechanical Structure

Body, Coxa, Femur and Tibia:

30 + 90 + 60 + 30 = 210 g

### Actuators and Electronics

MG90S Servos: 241.2 g

Raspberry Pi Pico: 3 g

PCA9685 Servo Drivers: 18 g

Battery: 100 g

Buck Converter: 12 g

Switch: 2 g

Total:

241.2 + 3 + 18 + 100 + 12 + 2 = 376.2 g

### Preliminary Total Robot Weight

Mechanical Structure + Actuators and Electronics:

210 + 376.2 = 586.2 g

| Category | Estimated Weight (g) |
|---|---:|
| Mechanical Structure | 210 |
| Actuators and Electronics | 376.2 |
| **Preliminary Estimated Total** | **586.2** |

The current preliminary estimated robot weight is:

**586.2 g (approximately 0.586 kg)**

This value does not yet include all potential additional components, such as:

- Servo mounting brackets.
- Screws, nuts and bolts.
- Wiring and connectors.
- Additional structural components.
- Other mounting hardware.
- Any components not currently included in the weight estimate.

Therefore, 586.2 g should be treated as a preliminary subtotal based on the currently listed components, rather than the final assembled robot weight.

The final total weight will need to be updated once the mechanical design is completed and all components are accounted for.

---

## 7. Next Steps

The following tasks will be carried out as the project progresses:

1. Verify the individual component weights using datasheets or physical measurements.
2. Confirm the final mechanical component dimensions and materials.
3. Update the mechanical structure weight following CAD development.
4. Include mounting brackets, fasteners, wiring and additional hardware.
5. Calculate the actual total robot weight.
6. Determine the robot's centre of mass.
7. Analyse the mass distribution between the body and individual legs.
8. Use the updated mass properties for subsequent joint torque calculations and mechanical optimisation.

This weight analysis will be updated continuously as the mechanical design develops and more accurate component data becomes available.
