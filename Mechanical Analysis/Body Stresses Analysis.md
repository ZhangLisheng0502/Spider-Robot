# Body Stresses Analysis

## 1. Objective

The objective of this analysis is to establish the structural analysis principles required for the Spider hexapod robot.

The analysis focuses on understanding the main loading conditions, evaluating structural strength and stiffness, identifying potential failure modes, and establishing appropriate design considerations.

The main components of interest include:

- Femur and Tibia
- Proximal Leg
- Servo Mounts
- Joint Brackets
- Mechanical Connections

The aim is to achieve a reliable and lightweight structure while maintaining sufficient strength, stiffness and stability.

---

## 2. Stress and Strain Fundamentals

### 2.1 Normal Stress

Normal stress occurs when a force acts perpendicular to a cross-sectional area.

$$
\sigma = \frac{F}{A}
$$

Where:

- $\sigma$ = Normal Stress (Pa or MPa)
- $F$ = Applied Force (N)
- $A$ = Cross-sectional Area (m² or mm²)

### 2.2 Strain

Strain describes the relative deformation of a component.

$$
\varepsilon = \frac{\Delta L}{L_0}
$$

Where:

- $\varepsilon$ = Strain (dimensionless)
- $\Delta L$ = Change in Length
- $L_0$ = Original Length

### 2.3 Hooke's Law

Within the linear elastic region:

$$
\sigma = E\varepsilon
$$

Where $E$ is Young's Modulus, representing the material's elastic stiffness.

---

## 3. Main Loading Conditions

### 3.1 Tension and Compression

- **Tension:** Pulling forces cause a component to elongate.
- **Compression:** Pushing forces cause a component to shorten.

The average normal stress is:

$$
\sigma = \frac{F}{A}
$$

Tension and compression must both be considered when evaluating structural loading.

Slender components subjected to compression may also be vulnerable to buckling.

### 3.2 Bending Stress

Bending occurs when a component is subjected to a bending moment.

For simple elastic beam bending:

$$
\sigma = \frac{My}{I}
$$

Maximum bending stress:

$$
\sigma_{\max} = \frac{M_{\max}y_{\max}}{I}
$$

Where:

- $M$ = Bending Moment (N·mm or N·m)
- $y$ = Distance from the Neutral Axis
- $I$ = Second Moment of Area (mm⁴ or m⁴)

For a rectangular cross-section:

$$
I = \frac{bh^3}{12}
$$

A larger second moment of area generally increases resistance to bending and reduces bending stress and deflection under equivalent conditions.

### 3.3 Shear Stress

Shear stress occurs when forces act parallel to a cross-sectional area, tending to cause adjacent material layers to slide relative to each other.

For average direct shear stress:

$$
\tau = \frac{F}{A}
$$

For an idealised bolt in double shear with equal load distribution:

$$
\tau = \frac{F}{2A}
$$

Where $\tau$ is Shear Stress.

Actual connections may have more complex load distributions and should be evaluated accordingly.

### 3.4 Torsion

Torsion occurs when a component is subjected to a twisting torque.

For a circular shaft:

$$
\tau = \frac{Tr}{J}
$$

Maximum torsional shear stress:

$$
\tau_{\max} = \frac{TR}{J}
$$

For a solid circular shaft:

$$
J = \frac{\pi d^4}{32}
$$

Where:

- $T$ = Applied Torque (N·mm or N·m)
- $r$ = Radial Distance
- $R$ = Outer Radius
- $J$ = Polar Second Moment of Area (mm⁴ or m⁴)

The maximum torsional shear stress occurs at the outer surface of a circular shaft.

---

## 4. Buckling

Buckling is a structural instability that can occur when a slender component is subjected to compression.

For an ideal elastic column, the Euler critical buckling load is:

$$
P_{cr} = \frac{\pi^2EI}{L_{\mathrm{eff}}^2}
$$

Where:

- $P_{cr}$ = Critical Buckling Load (N)
- $E$ = Young's Modulus
- $I$ = Second Moment of Area
- $L_{\mathrm{eff}}$ = Effective Column Length

Buckling resistance increases with greater material stiffness and second moment of area, and decreases with increasing effective length.

The Euler equation assumes an ideal slender column. Its assumptions, including boundary conditions and elastic behaviour, must be considered before applying it to an actual component.

---

## 5. Strength, Stiffness and Failure Modes

### 5.1 Strength vs Stiffness

**Strength** describes the ability of a component to withstand applied loads without material failure.

**Stiffness** describes the ability of a component to resist deformation under applied loads.

For bending, flexural rigidity is:

$$
EI
$$

Where:

- $E$ = Young's Modulus (Material Property)
- $I$ = Second Moment of Area (Geometric Property)

A component may have sufficient strength but still deform excessively. Therefore, both strength and stiffness must be considered during structural design.

### 5.2 Potential Failure Modes

The main failure modes relevant to the Spider structure include:

- Tensile Failure
- Compressive Failure
- Bending Failure
- Shear Failure
- Torsional Failure
- Buckling
- Fatigue Failure

Different components may experience multiple loading conditions and failure mechanisms simultaneously.

### 5.3 Fatigue

Fatigue is progressive material damage caused by repeated or cyclic loading.

The typical fatigue process involves:

1. Crack Initiation
2. Crack Propagation
3. Final Fracture

Stress concentrations around holes, notches and sharp corners can increase local stresses and contribute to fatigue crack initiation.

For a cyclic stress:

$$
\sigma_a = \frac{\sigma_{\max}-\sigma_{\min}}{2}
$$

Where:

- $\sigma_a$ = Stress Amplitude
- $\sigma_{\max}$ = Maximum Stress
- $\sigma_{\min}$ = Minimum Stress

An S–N curve relates stress amplitude to the number of cycles to failure.

In general, higher stress amplitudes result in shorter fatigue lives under comparable conditions.

---

## 6. Factor of Safety

The Factor of Safety (FoS) provides a margin between the selected failure criterion and the expected applied loading.

### 6.1 Against Yielding

$$
FoS = \frac{\sigma_y}{\sigma_{\mathrm{applied}}}
$$

Where:

- $\sigma_y$ = Material Yield Strength
- $\sigma_{\mathrm{applied}}$ = Applied Stress

### 6.2 Against Buckling

$$
FoS_{\mathrm{buckling}} =
\frac{P_{cr}}{P_{\mathrm{applied}}}
$$

Where:

- $P_{cr}$ = Critical Buckling Load
- $P_{\mathrm{applied}}$ = Applied Compressive Load

The appropriate failure criterion must be selected for each structural component.

A suitable FoS should account for loading uncertainty, material variability, manufacturing limitations and the consequences of failure.

Excessively high safety margins may result in unnecessary mass and increased actuator loading.

---

## 7. Engineering Considerations for the Spider

The following considerations will guide future structural design and optimisation.

| Design Consideration | Engineering Implication |
|---|---|
| Cross-sectional Area | Influences average normal stress |
| Cross-sectional Geometry | Influences bending resistance through $I$ |
| Material Selection | Influences strength and elastic stiffness |
| Component Length | Influences bending and buckling behaviour |
| Joint and Bracket Geometry | Influences load transfer and stress concentration |
| Component Mass | Influences actuator loading and joint torque |
| Repeated Loading | Influences fatigue performance |
| Connections and Fasteners | Require consideration of shear and local stresses |

Reducing unnecessary distal mass can also reduce the gravitational moment acting on proximal joints.

Structural optimisation must balance:

- Strength
- Stiffness
- Stability
- Fatigue Resistance
- Weight
- Manufacturing Constraints

The objective is not simply to maximise strength, but to achieve an appropriate balance between structural performance and mass.

---

## 8. Future Analysis and Validation

Quantitative structural analysis will be developed once the following design parameters are confirmed:

- Final component geometry and dimensions
- Material properties
- Servo positions and mounting arrangements
- Expected loading conditions
- Boundary conditions and joint constraints
- Manufacturing method

The next steps are:

1. Identify critical structural components.
2. Determine realistic loading conditions.
3. Identify critical cross-sections and potential failure locations.
4. Perform preliminary analytical calculations.
5. Evaluate strength, stiffness, buckling and relevant safety margins.
6. Validate the design using CAD mass properties and, where appropriate, Finite Element Analysis (FEA).
7. Refine the geometry to achieve an appropriate strength-to-weight and stiffness-to-weight balance.

FEA results should be interpreted alongside analytical calculations, realistic boundary conditions and appropriate mesh settings.

---

## 9. Conclusion

Structural design of the Spider requires more than ensuring that components do not break under static loads.

Strength, stiffness, buckling resistance, fatigue performance and component weight must all be considered.

This analysis establishes the theoretical foundation for future structural calculations and design optimisation of the Spider's legs, joints and mounting structures.

Quantitative conclusions and validation results will be added once the final geometry, materials and loading conditions are established.
