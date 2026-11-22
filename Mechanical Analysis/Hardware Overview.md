# Spider Robot – Hardware Overview

## 1. Project Overview

This project involves the design and development of a six-legged (hexapod) robot through Manchester Robotics Society.

The robot consists of mechanical components, actuators, electronic hardware, a power supply system and a control system.

## 2. Mechanical Components

| Component | Quantity | Approx. Individual Weight |
|---|---:|---:|
| Body | 1 | ~30 g |
| Coxa | 6 | ~15 g |
| Femur | 6 | ~10 g |
| Tibia | 6 | ~5 g |

## 3. Actuation System

- Servo motor: MG90S Micro Servo
- Quantity: 20 (18 required)
- Servo type: Metal gear micro servo

## 4. Electronic Components

| Component | Quantity |
|---|---:|
| Battery | 1 |
| Raspberry Pi | 1 |
| PCA9685 Servo Driver | 2 |
| Buck Converter | 1 |
| Switch | 1 |

## 5. Power System

The power system includes a battery and a buck converter.

The buck converter is used to regulate the voltage supplied to the relevant electronic components.

## 6. Control System

The Raspberry Pi acts as the main controller.

The PCA9685 servo driver provides PWM control signals to the servos.

## 7. Current Design Status

- Hardware components identified.
- Main mechanical components identified.
- Servo motors and electronic components selected.
- Mechanical design and integration are ongoing.
