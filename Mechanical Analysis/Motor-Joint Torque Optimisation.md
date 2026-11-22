# Motor-Joint Torque Optimisation

## 1. Objective

The objective of this preliminary mechanical analysis is to understand the factors affecting joint torque in a robotic leg and identify potential mechanical design strategies to reduce the torque demand on the actuators.

The focus is on the relationship between mass, centre of mass, lever arm, leg configuration and servo placement.

At this stage, the Spider robot's final dimensions, joint geometry, component positions and mechanical configuration have not yet been determined. Therefore, this analysis focuses on engineering principles and preliminary design considerations rather than actual robot torque calculations.

---

## 2. Fundamentals of Torque

Torque is the rotational effect produced by a force acting about a pivot or rotational axis.

The magnitude of torque is given by:

$$
\tau = Fr_{\perp}
$$

where:

- $\tau$ = torque (N·m)
- $F$ = applied force (N)
- $r_{\perp}$ = perpendicular distance from the rotational axis to the force's line of action (m)

For a force applied at a position $r$ with an angle $\theta$ between the position vector and the force vector:

$$
\tau = rF\sin\theta
$$

This shows that torque depends on both the magnitude of the force and its effective lever arm.

For a component subjected to gravity:

$$
F = mg
$$

Therefore, its gravitational torque about a joint can be expressed as:

$$
\tau = mgr_{\perp}
$$

This relationship indicates that increasing either the component mass or its distance from the joint increases the gravitational torque required to support it.

---

## 3. Effect of Leg Orientation on Gravitational Torque

The gravitational torque acting on a robotic leg changes as the leg rotates.

For a simplified single-link model with the leg angle $\alpha$ measured from the horizontal:

$$
\tau = mgr\cos\alpha
$$

where:

- $m$ = mass of the leg
- $g$ = gravitational acceleration
- $r$ = distance from the joint to the centre of mass
- $\alpha$ = angle of the leg measured from the horizontal

Under this simplified model:

- When the leg is horizontal, the gravitational torque is at its maximum.
- As the leg rotates towards a vertical position, the perpendicular distance between the joint and the gravitational force's line of action decreases.
- When the leg is vertical, the gravitational torque about the relevant axis is theoretically zero if the gravitational force acts through the joint axis.

The leg still experiences gravitational force when it is vertical. However, the gravitational force produces little or no rotational moment about that particular axis.

This demonstrates why the required joint torque depends not only on component mass but also on the leg configuration.

---

## 4. Centre of Mass and Mass Distribution

The centre of mass (CoM) is the point at which the mass of an object can be considered to be concentrated when analysing its gravitational effect.

For a uniform rod, the centre of mass is located at its midpoint.

For example, consider a uniform femur segment with:

- Length: $100\text{ mm}$
- Mass: $20\text{ g}$

Its centre of mass is located at:

$$
r_{\text{CoM}} = \frac{L}{2} = 50\text{ mm}
$$

When the leg is horizontal, its gravitational torque about the proximal joint is:

$$
\tau = mg r_{\text{CoM}}
$$

Converting the quantities into SI units:

$$
m = 0.020\text{ kg}
$$

$$
r_{\text{CoM}} = 0.050\text{ m}
$$

$$
\tau = 0.020\times9.81\times0.050
$$

$$
\boxed{\tau = 0.00981\text{ N}\cdot\text{m}}
$$

This example illustrates how the mass distribution of a leg segment directly affects the torque required at its joint.

For a leg containing multiple components, the total gravitational torque can be estimated by considering the individual masses and their respective distances from the joint:

$$
\tau_{\text{total}} = \sum_i m_i g r_i
$$

This simplified expression assumes the relevant gravitational moments act in the same direction and the components are considered in the corresponding maximum-torque orientation. For an actual robot, the individual perpendicular lever arms and orientations must be considered.

---

## 5. Effect of Distal Mass

Distal mass refers to mass located farther away from a proximal joint.

A component located farther from a joint produces a larger moment because it has a longer lever arm.

For the same mass:

$$
\tau = mgr
$$

Therefore:

$$
\tau \propto r
$$

Consider a hypothetical $20\text{ g}$ component.

### Case A — Component located 20 mm from the joint

$$
\tau = 0.020\times9.81\times0.020
$$

$$
\tau = 0.003924\text{ N}\cdot\text{m}
$$

### Case B — Component located 100 mm from the joint

$$
\tau = 0.020\times9.81\times0.100
$$

$$
\tau = 0.01962\text{ N}\cdot\text{m}
$$

The second configuration produces five times the gravitational torque of the first.

This highlights the importance of controlling distal mass when designing robotic legs.

Potential design considerations include:

- Minimising unnecessary material in distal leg sections.
- Avoiding excessive mass at the end of a leg.
- Considering the location of actuators and other components.
- Maintaining structural strength while reducing mass.

Reducing distal mass can improve the mechanical efficiency of the leg and reduce the torque demand on upstream joints.

---

## 6. Servo Placement and Its Effect on Joint Torque

Servo placement is an important consideration in robotic leg design.

A servo has two mechanical roles:

1. It produces torque to actuate its own joint.
2. Its physical mass contributes to the gravitational torque experienced by upstream joints.

Therefore, servo placement can affect the torque requirements of more than one joint.

For example, placing a servo farther away from a proximal joint increases the lever arm of the servo's own mass.

The gravitational torque contributed by the servo can be estimated as:

$$
\tau_{\text{servo mass}} = m_{\text{servo}}gr
$$

Consider a hypothetical servo with a mass of $13.4\text{ g}$.

### Servo located 30 mm from the proximal joint

$$
\tau = 0.0134\times9.81\times0.030
$$

$$
\tau \approx 0.00394\text{ N}\cdot\text{m}
$$

### Servo located 100 mm from the proximal joint

$$
\tau = 0.0134\times9.81\times0.100
$$

$$
\tau \approx 0.01315\text{ N}\cdot\text{m}
$$

The servo positioned 100 mm from the joint contributes approximately 3.33 times the gravitational torque compared with the servo located 30 mm away.

This suggests that actuator placement should be considered carefully during the mechanical design process, particularly when the actuator is carried by an upstream joint.

However, moving a servo closer to a joint is not always possible or optimal. The design must also consider:

- Joint geometry.
- Mechanical interference.
- Transmission requirements.
- Structural rigidity.
- Assembly accessibility.
- Cable routing.
- Range of motion.

---

## 7. Preliminary Mechanical Optimisation Strategies

### 7.1 Mass Reduction

Reducing the mass of a leg segment decreases the gravitational force acting on the joint.

Since:

$$
\tau = mgr
$$

for a fixed configuration and lever arm:

$$
\tau \propto m
$$

Reducing component mass therefore reduces the gravitational torque required to support the component.

Potential approaches include:

- Removing unnecessary material.
- Optimising component geometry.
- Using suitable lightweight materials.
- Reducing excessive wall thickness where structural requirements permit.

Mass reduction must not compromise the structural strength or stiffness required during robot operation.

### 7.2 Optimising Mass Distribution

The location of mass can be as important as the total mass.

A component located close to a joint produces a smaller gravitational moment than the same component located farther away.

Therefore, the mechanical design should consider both:

- Total component mass.
- Distance of the component's centre of mass from the relevant joint.

This is particularly important for proximal joints supporting multiple leg sections and actuators.

### 7.3 Optimising Leg Geometry

Leg geometry affects the mechanical leverage acting on each joint.

Changing segment lengths or joint positions can alter:

- The gravitational moment acting on the joint.
- The robot's reachable workspace.
- The mechanical leverage.
- The leg's movement range.
- The interaction between adjacent leg segments.

Geometry should therefore be optimised while maintaining the required movement capability and functional constraints of the robot.

### 7.4 Servo Placement Optimisation

Servo positioning should aim to balance:

- Reduced upstream gravitational torque.
- Required actuation torque.
- Available space.
- Joint movement.
- Mechanical complexity.
- Ease of assembly.

Placing heavy components closer to the robot body or proximal joints may reduce the gravitational torque acting on upstream joints.

However, the benefits must be evaluated against the complexity of the resulting mechanical arrangement.

### 7.5 Structural Lightweighting

The leg segment and servo mounting structure should provide sufficient strength and stiffness while minimising unnecessary mass.

Potential approaches include:

- Optimising cross-sectional geometry.
- Using ribs or reinforcement features strategically.
- Removing material from low-stress regions.
- Maintaining material around mounting holes and load-bearing regions.
- Minimising unnecessary bracket mass.

The aim is not simply to produce the lightest component, but to achieve an appropriate balance between mass, stiffness, strength and manufacturability.

---

## 8. Preliminary Design Considerations

Based on the principles discussed, the following considerations should be taken into account during the future Spider leg design process:

- Minimise unnecessary mass in the leg structure.
- Pay particular attention to the mass of components located far from proximal joints.
- Consider servo mass as part of the upstream joint loading.
- Evaluate the centre of mass of each leg segment.
- Optimise segment geometry without compromising the required movement range.
- Design the servo mounting structure to be lightweight but sufficiently rigid.
- Consider the mechanical arrangement of the proximal joint and servo together rather than as isolated components.

These considerations provide a preliminary framework for the future mechanical design and optimisation of the Spider's leg assembly.

---

## 9. Limitations of the Preliminary Analysis

This analysis is based on simplified mechanical models and illustrative calculations.

The following information is currently unavailable or has not yet been finalised:

- Actual leg segment dimensions.
- Final joint positions.
- Actual component mass distribution.
- Servo mounting locations.
- Final leg configuration.
- Detailed robot movement and gait requirements.
- Mechanical transmission arrangement.
- Dynamic loading during walking.

Consequently, the torque values presented in this document are illustrative examples and should not be interpreted as the actual torque requirements of the Spider robot.

Static gravitational torque is only one component of the total actuator demand. During actual operation, additional torque may be required due to acceleration, deceleration, dynamic movement, friction, impact loading and other mechanical effects.

---

## 10. Future Work

The next stage of the project will involve applying these preliminary principles to the actual mechanical design.

Future work includes:

1. Establishing the leg geometry and joint positions.
2. Creating the proximal leg segment and joint design in Fusion 360.
3. Determining the actual component masses and centre-of-mass locations.
4. Calculating the gravitational torque acting on each relevant joint.
5. Evaluating the selected servo against the calculated torque requirements.
6. Identifying potential structural and mass optimisation opportunities.
7. Comparing alternative mechanical designs.
8. Validating the final design through physical testing.

The preliminary analysis provides the theoretical foundation for these future design, calculation and optimisation tasks.

---

## 11. Conclusion

Joint torque is strongly influenced by component mass, mass distribution, lever arm length and leg configuration.

The preliminary analysis demonstrates that reducing mass, controlling distal mass, optimising servo placement and improving structural geometry are potential strategies for reducing the mechanical torque demand on robotic leg joints.

These principles will be applied during the subsequent CAD and mechanical design stages, once the Spider's actual geometry and component arrangement have been established.
