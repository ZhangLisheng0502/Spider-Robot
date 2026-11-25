# Hardware Overview

## 1. Project Overview

The Manchester Robotics Society Spider project involves the design and development of a six-legged (hexapod) robot.

The hardware system consists of three main sections:

- Control System
- Actuation System
- Power System

The mechanical structure provides the supporting frame and mounting points for the electronic components and actuators.

The current hardware configuration is based on the latest shared `RoboSoc-Spyder-MASTER_FILE.xlsx` Assembly sheet.

---

## 2. Control System

### 2.1 Raspberry Pi Pico 2W

**Component:** Pico 2W RP2350 Microcontroller Development Board (SC1634)

**Quantity:** 1

The Raspberry Pi Pico 2W is the main microcontroller responsible for executing the robot control program.

Its main functions include:

- Processing control commands.
- Generating control signals for the servo driver.
- Managing communication with external devices.
- Coordinating the movement of the robot's legs.

Product reference: [Raspberry Pi Pico 2W SC1634](https://cpc.farnell.com/raspberry-pi/sc1634/raspberry-pi-pico-2w-with-header/dp/SC21692)

### 2.2 PCA9685 Servo Controller

**Component:** PCA9685 16-channel PWM Servo Controller

**Quantity:** 2

The PCA9685 generates PWM signals to control the servo positions.

Each PCA9685 provides 16 PWM channels. With two boards, the theoretical total is:

16 × 2 = 32 PWM channels.

The robot uses 18 MG90S servos, so the two boards provide sufficient channel capacity.

The PCA9685 communicates with the Pico through the I²C interface.

Its main functions include:

- Generating PWM control signals.
- Controlling multiple servos independently.
- Reducing the need for individual PWM outputs from the microcontroller.

Product reference: [PCA9685 Servo Controller](https://www.amazon.co.uk/DollaTek-PCA9685-Channel-12-bit-Driver/dp/B0BKZC1XWR)

---

## 3. Actuation System

### 3.1 MG90S Metal Gear Micro Servo

**Component:** MG90S Micro Servo (Metal Gears)

**Quantity:** 18

The MG90S servos provide the actuation for the robot's joints.

The current configuration uses 18 servos across the six legs.

Their functions include:

- Producing joint rotation.
- Positioning the leg segments.
- Supporting coordinated leg movement during different gaits.

Typical MG90S reference specifications:

| Parameter | Reference value |
|---|---|
| Operating voltage | 4.8–6.0 V |
| Stall torque | 1.8 kgf·cm at 4.8 V; 2.2 kgf·cm at 6.0 V |
| Operating speed | 0.10 s/60° at 4.8 V; 0.08 s/60° at 6.0 V |
| Weight | Approximately 13.4 g |

These are reference specifications for a conventional MG90S. The exact performance of the purchased units should be checked against the supplier's specification and verified after delivery.

Product reference: [MG90S Metal Gear Micro Servo](https://www.aliexpress.com/item/1005004550692203.html)

---

## 4. Power System

### 4.1 2S LiPo Battery

**Component:** 2S LiPo Battery with Recharging Capabilities

**Quantity:** 1

The battery provides the main electrical energy source for the robot.

A conventional 2S LiPo battery has:

- Nominal voltage: 7.4 V.
- Fully charged voltage: 8.4 V.

The battery supplies the power system, which must provide suitable voltage levels for the servos and control electronics.

Product reference: [2S LiPo Battery](https://www.amazon.co.uk/Yangers-Rechargeable-Replacement-Radiomaster-Transmitter/dp/B0DZ6ZK1MZ)

The battery capacity, discharge rating and exact connector specifications should be confirmed from the purchased product.

### 4.2 XL4015 DC-DC Converter

**Component:** XL4015 Adjustable Step-Down DC-DC Converter (5 A, 75 W)

**Quantity:** 1

The XL4015 is an adjustable buck converter used to reduce the battery voltage to a suitable lower voltage.

The listed module specifications are:

- Input voltage range: 4.0–38 V.
- Adjustable output voltage: 1.25–36 V.
- Advertised maximum current: 5 A.
- Advertised maximum power: 75 W.

The actual usable output current and power depend on operating conditions, cooling and the module implementation.

The output voltage must be configured and measured before connecting the servos or other electronics.

Product reference: [XL4015 DC-DC Converter](https://www.aliexpress.us/item/3256805953598799.html)

### 4.3 Wiring

Wires are listed separately in the Assembly sheet and will be sourced independently.

The wiring system must provide:

- Battery power distribution.
- Servo power connections.
- PWM signal connections.
- I²C communication between the Pico and PCA9685 boards.
- A common ground reference where required.

---

## 5. Mechanical Structure

The mechanical structure consists of:

| Component | Quantity | Estimated individual weight |
|---|---:|---:|
| Body | 1 | ~30 g |
| Coxa | 6 | ~15 g |
| Femur | 6 | ~10 g |
| Tibia | 6 | ~5 g |

The body provides the central supporting structure for the robot.

The Coxa, Femur and Tibia form the main leg segments.

The mechanical design must accommodate:

- Servo mounting locations.
- Joint connections.
- Electronic component mounting.
- Battery positioning.
- Wiring routes.
- Adequate structural strength and stiffness.

The listed mechanical weights are preliminary estimates and should be verified using the final manufactured components.

---

## 6. Current Hardware Configuration

| Subsystem | Component | Quantity |
|---|---|---:|
| Control | Raspberry Pi Pico 2W RP2350 | 1 |
| Servo control | PCA9685 16-channel controller | 2 |
| Actuation | MG90S metal gear servo | 18 |
| Power | 2S LiPo battery | 1 |
| Power regulation | XL4015 buck converter | 1 |
| Wiring | Connecting wires | As required |

The current listed component budget is approximately £67.86, excluding any additional wiring costs.

---

## 7. Electrical Design Considerations

The following points must be considered before finalising the circuit design:

1. **Servo voltage:** MG90S servos typically operate at 4.8–6.0 V. They should not be connected directly to the fully charged 2S battery voltage.
2. **Current capacity:** The power supply must be sized for the combined servo current under realistic simultaneous movement and peak loading conditions.
3. **Buck converter:** The XL4015 output voltage and actual current capability must be verified under load.
4. **Power distribution:** Servo power should be supplied through an appropriately rated power distribution arrangement rather than relying on the microcontroller board's power output.
5. **Common ground:** The Pico, PCA9685 boards and servo power supply require an appropriate common ground reference for reliable PWM signalling.
6. **Battery protection:** The battery requires suitable charging, voltage monitoring and protection arrangements.

The advertised 5 A converter rating should not automatically be assumed sufficient for all 18 servos operating simultaneously.

---

## 8. Current Development Stage

The main electronic components are now listed in the shared Assembly sheet, and the team has started ordering the parts.

The next stages include:

- Confirming the delivered component specifications.
- Designing the electrical circuit.
- Verifying the servo power requirements.
- Establishing the Pico-to-PCA9685 communication.
- Integrating the electronic components with the mechanical structure.
- Testing individual servo operation before full robot assembly.

---

## 9. Outstanding Questions

The following information still needs confirmation:

- Exact battery capacity and maximum discharge current.
- Actual MG90S stall current and operating characteristics of the delivered units.
- XL4015 output voltage setting and continuous current capability.
- Final wiring and power distribution arrangement.
- Mounting locations for the battery, controllers and converter.
- Whether the previously listed ZF DB3C-A1LB switch is still required, as it is absent from the latest Assembly sheet.

These details should be confirmed before finalising the electrical design and overall system integration.
