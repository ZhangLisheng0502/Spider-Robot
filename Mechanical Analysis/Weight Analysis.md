# Weight Analysis

## 1. Objective

The purpose of weight analysis is to estimate the total mass of the Spider hexapod robot and understand how its mass is distributed across the mechanical and electronic systems.

Weight analysis is important because robot mass directly affects:

- Required joint torque.
- Ground reaction forces.
- Structural stresses.
- Contact pressure.
- Overall stability and mobility.

The estimates in this document are based on the latest shared `RoboSoc-Spyder-MASTER_FILE.xlsx` Assembly sheet and available component specifications.

---

## 2. Mechanical Component Weight

The current estimated mechanical component weights are:

| Component | Quantity | Individual weight | Total weight |
|---|---:|---:|---:|
| Body | 1 | ~30 g | ~30 g |
| Coxa | 6 | ~15 g | ~90 g |
| Femur | 6 | ~10 g | ~60 g |
| Tibia | 6 | ~5 g | ~30 g |
| **Total** | | | **~210 g** |

The mechanical mass is therefore:

$$
m_{\mathrm{mechanical}}
=30+(6\times15)+(6\times10)+(6\times5)
$$

$$
\boxed{m_{\mathrm{mechanical}}\approx210\ \mathrm{g}}
$$

These values are preliminary estimates. Actual manufactured component weights should be measured once the parts are available.

---

## 3. Actuator Weight

The current Assembly sheet lists 18 MG90S metal gear micro servos.

A conventional MG90S reference weight is approximately 13.4 g per servo.

The estimated total servo mass is:

$$
m_{\mathrm{servos}}=18\times13.4
$$

$$
\boxed{m_{\mathrm{servos}}\approx241.2\ \mathrm{g}}
$$

The exact purchased servo weight should be verified after delivery.

---

## 4. Electronic Component Weight

The updated Assembly sheet contains the following electronic components:

| Component | Quantity | Weight status |
|---|---:|---|
| Raspberry Pi Pico 2W RP2350 | 1 | To be verified |
| PCA9685 Servo Controller | 2 | To be verified |
| 2S LiPo Battery | 1 | To be verified |
| XL4015 DC-DC Converter | 1 | To be verified |
| Connecting wires | As required | To be measured |

The current spreadsheet provides component names, quantities and purchasing links, but does not provide confirmed weights for these components.

Therefore, their masses should not be treated as known values.

The previously used estimates for the Pico, PCA9685 boards, battery and buck converter should be replaced by the actual specifications or measured weights of the purchased components.

The previously listed ZF DB3C-A1LB switch is not included in the latest Assembly sheet. Its inclusion in the final mass calculation depends on whether the team still intends to use it.

---

## 5. Current Estimated Mass

Based on the mechanical component estimates and the conventional MG90S reference weight, the currently quantifiable mass is:

$$
m_{\mathrm{known}}
=
m_{\mathrm{mechanical}}
+
m_{\mathrm{servos}}
$$

$$
m_{\mathrm{known}}=210+241.2
$$

$$
\boxed{m_{\mathrm{known}}\approx451.2\ \mathrm{g}}
$$

This is a partial mass estimate, not the final robot mass.

The final robot mass must also include:

- Battery.
- Raspberry Pi Pico 2W.
- PCA9685 boards.
- XL4015 converter.
- Connecting wires.
- Servo brackets and mounting components.
- Screws, nuts and other fasteners.
- Any additional mechanical parts.

Therefore:

$$
m_{\mathrm{total}}
=
m_{\mathrm{known}}
+
m_{\mathrm{electronics}}
+
m_{\mathrm{additional}}
$$

Where $m_{\mathrm{electronics}}$ and $m_{\mathrm{additional}}$ must be determined from actual component weights.

---

## 6. Weight Distribution and Joint Torque

The distribution of mass is as important as the total mass.

Mass located further from a joint produces a larger gravitational moment.

For a component with mass $m$ at perpendicular distance $r$ from a joint:

$$
\tau=mgr
$$

For multiple components:

$$
\tau_{\mathrm{total}}=\sum_i m_i g r_i
$$

Where:

- $m_i$ = mass of component $i$.
- $g$ = gravitational acceleration.
- $r_i$ = perpendicular distance from the joint axis to the component's centre of mass.

For the Spider robot, the mass of distal components such as the Femur, Tibia and foot can contribute significantly to the torque required at proximal joints.

Servo mass must also be considered. A servo mounted further away from a joint can increase the gravitational moment acting on that joint.

This makes component placement an important part of mechanical optimisation.

---

## 7. Engineering Implications

The preliminary mass analysis suggests several design considerations:

1. **Reduce unnecessary distal mass:** Minimising mass further from proximal joints can reduce gravitational torque requirements.
2. **Optimise component placement:** Heavy components such as the battery should be positioned carefully to manage the overall centre of gravity.
3. **Consider servo mass:** The location and orientation of servos affect the loading of the leg structure.
4. **Avoid unnecessary structural mass:** Mechanical components should provide sufficient strength and stiffness without excessive weight.
5. **Verify estimates:** Final calculations should use actual manufactured-part weights and purchased component specifications.

---

## 8. Limitations

The current analysis is preliminary because:

- Mechanical part weights are estimates rather than measured values.
- Electronic component weights have not yet been confirmed.
- Additional brackets, screws, wiring and mounting hardware are not included.
- Final CAD geometry and component positions may change.
- The final centre of gravity has not yet been calculated.

Consequently, the current value of approximately 451.2 g should only be treated as the mass of the currently quantifiable components.

---

## 9. Next Steps

Once the purchased components arrive and the mechanical design is finalised:

1. Measure the actual weight of each mechanical component.
2. Record the actual weight of the servos, battery, controllers and converter.
3. Include wiring, brackets, screws and other mounting hardware.
4. Calculate the updated total robot mass.
5. Determine the position of each component's centre of mass.
6. Calculate the overall centre of gravity.
7. Update the joint torque analysis using the revised mass distribution.

The final weight analysis should be based on the assembled robot rather than preliminary estimates alone.
