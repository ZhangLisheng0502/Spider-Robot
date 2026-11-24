# Ground Contact Pressure Analysis

## 1. Introduction

Ground contact pressure analysis investigates how the spider robot's feet interact mechanically with the ground. It considers the distribution of normal forces, contact area, local pressure and the effect of eccentric loading.

The main objectives are to:

- Estimate the contact pressure under each supporting foot.
- Understand how foot geometry affects pressure.
- Evaluate non-uniform pressure distributions.
- Investigate the relationship between contact loading and robot stability.
- Identify design considerations for the spider's feet and support configuration.

The analysis is divided into five fundamental topics and four advanced topics.

---

# Part A — Fundamental Concepts

## 2. Contact Force and Ground Interaction

When a robot foot contacts the ground, the ground exerts a Ground Reaction Force (GRF) on the foot.

For a horizontal ground surface, the reaction force can be resolved into:

- Normal Force ($F_n$): perpendicular to the ground.
- Friction Force ($F_f$): parallel to the ground.

For static vertical equilibrium:

$$
\sum F_y=0
$$

If the robot's weight is $W=mg$, and $n$ supporting legs share the load equally under an idealised assumption:

$$
F_n=\frac{mg}{n}
$$

For example, if six legs support the robot equally:

$$
F_n=\frac{mg}{6}
$$

If only three legs support the robot:

$$
F_n=\frac{mg}{3}
$$

**Important:** Equal load sharing is a simplifying assumption. Actual leg loading depends on the centre of gravity (CoG), support geometry, gait, acceleration and ground conditions.

## 3. Contact Pressure

Contact pressure is the normal force distributed over the contact area.

The average contact pressure is:

$$
P_{\mathrm{avg}}=\frac{F_n}{A}
$$

Where:

- $F_n$ = normal contact force (N).
- $A$ = contact area (mm² or m²).
- $P_{\mathrm{avg}}$ = average contact pressure (MPa or Pa).

Useful unit conversion:

$$
1\ \mathrm{N/mm^2}=1\ \mathrm{MPa}
$$

Average pressure provides an initial estimate of ground loading. However, actual pressure may vary across the contact surface.

## 4. Contact Area and Foot Geometry

The contact area depends on foot geometry.

For a circular contact surface:

$$
A=\pi r^2=\frac{\pi d^2}{4}
$$

For a rectangular contact surface:

$$
A=LW
$$

Increasing the contact area reduces average pressure for a constant normal force.

However, a larger foot may increase weight, interfere with leg movement and increase the mass carried by the leg. Additional distal mass can also increase the torque required at proximal joints.

The actual contact area may be smaller than the nominal geometric area because of surface roughness, deformation and uneven ground.

## 5. Ground Reaction Force and Load Distribution

The normal reaction forces must satisfy force and moment equilibrium.

Vertical force equilibrium:

$$
\sum F_y=0
$$

Moment equilibrium:

$$
\sum M=0
$$

For a simplified two-support system with a total vertical load $W$, support spacing $L$, and the load acting at distance $x$ from support A:

$$
R_B=\frac{Wx}{L}
$$

$$
R_A=W-R_B
$$

This demonstrates that load distribution depends on the position of the centre of gravity, rather than being automatically equal between supporting legs.

For a hexapod robot, the actual distribution also depends on the selected gait and which legs are in contact with the ground.

## 6. Foot Design Optimisation

Foot design involves balancing contact pressure, weight, stability and mobility.

A simplified design pressure can be estimated using:

$$
P_{\mathrm{design}}=\frac{F_{n,\mathrm{design}}}{A_{\mathrm{contact}}}
$$

Important design considerations include:

- Sufficient contact area to reduce excessive pressure.
- Appropriate foot dimensions for the intended ground surface.
- Limited additional mass at the distal end of the leg.
- Adequate ground clearance and freedom of movement.
- Reliable contact under different supporting configurations.

---

# Part B — Advanced Analysis

## 7. Contact Pressure Distribution

### 7.1 Average Pressure vs Local Pressure

Average pressure assumes that the total normal force is distributed uniformly over the contact area.

However, real contact pressure is often non-uniform.

The local pressure can be expressed as a function of position:

$$
p=p(x,y)
$$

For a small surface element $dA$, the normal force acting on it is:

$$
dF=p(x,y)dA
$$

The total normal force is therefore:

$$
F_n=\int_A p(x,y)dA
$$

For a rectangular contact surface with constant width $b$ and pressure varying only along its length:

$$
F_n=b\int_{-L/2}^{L/2}p(x)dx
$$

The average pressure remains:

$$
P_{\mathrm{avg}}=\frac{F_n}{bL}
$$

However, the maximum local pressure may be significantly higher than the average pressure.

### 7.2 Example: Linear Pressure Distribution

Consider a rectangular contact surface:

- Length: $L=20$ mm
- Width: $b=10$ mm
- Pressure distribution:

$$
p(x)=0.2+0.02x
$$

Where $p$ is in MPa and $x$ is in mm, with $0\leq x\leq20$.

The total normal force is:

$$
F_n=b\int_0^{20}(0.2+0.02x)dx
$$

$$
F_n=10[0.2x+0.01x^2]_0^{20}
$$

$$
F_n=80\ \mathrm{N}
$$

The nominal contact area is:

$$
A=10\times20=200\ \mathrm{mm^2}
$$

Therefore:

$$
P_{\mathrm{avg}}=\frac{80}{200}=0.4\ \mathrm{MPa}
$$

The maximum local pressure occurs at $x=20$ mm:

$$
p_{\max}=0.2+0.02(20)=0.6\ \mathrm{MPa}
$$

This demonstrates that average pressure and maximum local pressure are not necessarily equal.

### 7.3 Engineering Implications

- Average pressure is useful for preliminary design comparisons.
- Local pressure is important when investigating peak loading.
- Non-uniform contact may produce local deformation or excessive surface stress.
- Foot geometry and loading position can significantly affect pressure distribution.

---

## 8. Hertzian Contact

### 8.1 Basic Contact Mechanism

Hertzian contact theory describes the elastic contact between curved surfaces.

For example, when a spherical foot contacts a flat rigid surface, the ideal initial point contact develops into a finite circular contact patch due to elastic deformation.

The pressure is highest at the centre and decreases towards the edge of the contact region.

For a sphere contacting a flat surface, the Hertz pressure distribution is:

$$
p(r)=p_0\sqrt{1-\frac{r^2}{a^2}}
$$

Where:

- $r$ = radial distance from the centre of contact.
- $a$ = contact radius.
- $p_0$ = maximum pressure at the centre.

At the centre:

$$
p(0)=p_0
$$

At the edge:

$$
p(a)=0
$$

### 8.2 Relationship Between Maximum and Average Pressure

The total normal force is obtained by integrating the pressure over the circular contact area.

Using a circular ring element:

$$
dA=2\pi r\,dr
$$

Therefore:

$$
F_n=2\pi\int_0^a p(r)r\,dr
$$

Substituting the Hertz pressure distribution:

$$
F_n=2\pi p_0\int_0^a
\sqrt{1-\frac{r^2}{a^2}}r\,dr
$$

The resulting relationship is:

$$
F_n=\frac{2}{3}\pi a^2p_0
$$

The projected circular contact area is:

$$
A=\pi a^2
$$

Therefore:

$$
P_{\mathrm{avg}}=\frac{F_n}{\pi a^2}
$$

Combining these expressions:

$$
\boxed{p_0=\frac{3}{2}P_{\mathrm{avg}}}
$$

Thus, the maximum Hertz contact pressure is 1.5 times the average pressure.

### 8.3 Hertz Contact Radius

For a sphere contacting a flat surface, the contact radius is:

$$
a=\left(\frac{3F_nR}{4E^*}\right)^{1/3}
$$

Where:

- $F_n$ = normal contact force.
- $R$ = sphere radius.
- $E^*$ = effective elastic modulus.

The effective modulus is:

$$
\frac{1}{E^*}
=
\frac{1-\nu_1^2}{E_1}
+
\frac{1-\nu_2^2}{E_2}
$$

Where $E_1,E_2$ are Young's moduli and $\nu_1,\nu_2$ are Poisson's ratios of the two contacting materials.

### 8.4 Important Trends

From the contact radius equation:

$$
a\propto F_n^{1/3}
$$

For fixed material properties and geometry, increasing the normal force increases the contact radius.

Since:

$$
p_0=\frac{3F_n}{2\pi a^2}
$$

The maximum pressure also increases with normal force.

For example, increasing the normal force by a factor of eight increases the contact radius by a factor of two and the maximum pressure by a factor of two.

### 8.5 Applicability and Limitations

Hertz theory assumes:

- Elastic deformation of the contacting bodies.
- Smooth contact surfaces.
- Small deformation relative to the dimensions of the bodies.
- No significant adhesion between the surfaces.

It is not directly appropriate for substantial plastic deformation or highly deformable materials undergoing large deformation.

For the spider project, Hertz theory is relevant if the foot has a curved contact surface. A flat-bottomed foot should instead be analysed using an appropriate flat-contact model.

---

## 9. Rectangular and Square Contact

### 9.1 Central Loading

For a rectangular foot with a centred normal load, a simplified uniform pressure assumption gives:

$$
P_{\mathrm{avg}}=\frac{F_n}{bL}
$$

Under symmetric loading, the pressure is uniform in this idealised model.

### 9.2 Eccentric Loading

When the load acts away from the geometric centre, the foot experiences an eccentric moment:

$$
M=F_ne
$$

Where $e$ is the eccentricity measured from the geometric centre.

Assuming a linear pressure distribution along the length:

$$
p(x)=p_0+kx
$$

Here, $x=0$ is the geometric centre, and $k$ represents the pressure gradient.

The total normal force is:

$$
F_n=b\int_{-L/2}^{L/2}(p_0+kx)dx
$$

Because $kx$ is an odd function over symmetric limits, its integral is zero:

$$
F_n=bp_0L
$$

Therefore:

$$
p_0=\frac{F_n}{bL}
$$

Taking moments about the geometric centre:

$$
F_ne=b\int_{-L/2}^{L/2}xp(x)dx
$$

The constant-pressure term contributes zero moment, giving:

$$
F_ne=\frac{bkL^3}{12}
$$

Thus:

$$
k=\frac{12F_ne}{bL^3}
$$

The maximum and minimum pressures occur at the two opposite edges:

$$
\boxed{
p_{\max,\min}
=
\frac{F_n}{bL}
\left(1\pm\frac{6e}{L}\right)
}
$$

The positive sign gives maximum pressure and the negative sign gives minimum pressure.

### 9.3 Middle Third Rule

For the entire rectangular surface to remain in contact, the minimum pressure must not be negative:

$$
p_{\min}\geq0
$$

Therefore:

$$
\frac{F_n}{bL}\left(1-\frac{6e}{L}\right)\geq0
$$

For a positive normal force:

$$
\boxed{e\leq\frac{L}{6}}
$$

This is known as the Middle Third Rule.

The load line must remain within the middle third of the contact length to maintain full contact under the assumed linear pressure model.

The middle third has total length $L/3$, extending $L/6$ on either side of the geometric centre.

At the limiting condition:

$$
e=\frac{L}{6}
$$

The minimum edge pressure becomes zero.

If:

$$
e>\frac{L}{6}
$$

The full-contact linear pressure model predicts negative pressure in part of the surface. Since an ordinary non-adhesive contact interface cannot transmit tensile force, the full-contact assumption is no longer valid. A partial-contact model is then required.

### 9.4 Example

Consider a rectangular foot:

- $L=30$ mm
- $b=20$ mm
- $F_n=60$ N
- $e=3$ mm

Average pressure:

$$
P_{\mathrm{avg}}=\frac{60}{20\times30}
=0.10\ \mathrm{MPa}
$$

Maximum pressure:

$$
p_{\max}=0.10\left(1+\frac{6\times3}{30}\right)
$$

$$
\boxed{p_{\max}=0.16\ \mathrm{MPa}}
$$

Minimum pressure:

$$
p_{\min}=0.10\left(1-\frac{6\times3}{30}\right)
$$

$$
\boxed{p_{\min}=0.04\ \mathrm{MPa}}
$$

Since:

$$
e=3\ \mathrm{mm}<\frac{30}{6}=5\ \mathrm{mm}
$$

The full-contact assumption is satisfied.

### 9.5 Square Contact and Two-Dimensional Eccentricity

For a square foot, the same one-direction analysis applies along either centre axis, using the corresponding side length.

For a rectangular surface with eccentricities in both directions, a linear full-contact pressure model can be written as:

$$
p(x,y)=
\frac{F_n}{bL}
+
\frac{12F_ne_x}{bL^3}x
+
\frac{12F_ne_y}{Lb^3}y
$$

Where:

- $e_x$ = eccentricity along the length direction.
- $e_y$ = eccentricity along the width direction.
- $x,y$ = coordinates measured from the geometric centre.

The model must be checked at the corners. If the calculated pressure becomes negative at any corner, the assumed full-contact condition is invalid.

---

## 10. Centre of Pressure and Stability

### 10.1 Centre of Pressure (CoP)

When pressure is distributed over a contact surface, the distributed forces can be replaced by an equivalent resultant normal force.

The point where this resultant acts is the Centre of Pressure (CoP).

For a rectangular foot with constant width $b$ and pressure varying along its length:

$$
F_n=b\int_{-L/2}^{L/2}p(x)dx
$$

The moment about the geometric centre is:

$$
M=b\int_{-L/2}^{L/2}xp(x)dx
$$

The equivalent resultant force acts at the CoP:

$$
M=F_nx_{\mathrm{CoP}}
$$

Therefore:

$$
\boxed{
x_{\mathrm{CoP}}=
\frac{b\int_{-L/2}^{L/2}xp(x)dx}{F_n}
}
$$

The CoP is the location of the resultant contact pressure, not the geometric centre of the foot.

### 10.2 Example: Linear Pressure Distribution

Consider:

$$
p(x)=0.10+0.02x
$$

Where pressure is in MPa, $x$ is in mm, $-15\leq x\leq15$, and the foot width is $b=20$ mm.

The total normal force is:

$$
F_n=20\int_{-15}^{15}(0.10+0.02x)dx
$$

$$
\boxed{F_n=60\ \mathrm{N}}
$$

The moment about the geometric centre is:

$$
M=20\int_{-15}^{15}x(0.10+0.02x)dx
$$

The odd-function term integrates to zero:

$$
M=20(0.02)\int_{-15}^{15}x^2dx
$$

$$
\boxed{M=900\ \mathrm{Nmm}}
$$

Therefore:

$$
x_{\mathrm{CoP}}=\frac{900}{60}
$$

$$
\boxed{x_{\mathrm{CoP}}=15\ \mathrm{mm}}
$$

The resultant acts at the positive edge of the contact surface, where the pressure is greatest.

### 10.3 Centre of Gravity vs Centre of Pressure

These two concepts must be distinguished.

**Centre of Gravity (CoG):**

- The equivalent point of application of the robot's weight.
- Determined by the mass distribution of the body, battery, electronics, servos and legs.
- Important for evaluating the robot's overall balance.

**Centre of Pressure (CoP):**

- The point of application of the resultant contact pressure.
- Determined by the pressure distribution between the foot and ground.
- Important for understanding local ground contact and resultant reaction forces.

The CoG describes where the robot's weight acts, whereas the CoP describes where the resultant ground contact pressure acts.

### 10.4 Support Polygon

The Support Polygon is the area enclosed by connecting the ground contact points of the supporting feet.

For a static robot on level ground, under the simplified assumption that gravity and vertical ground reactions are the only relevant external forces:

- If the vertical projection of the CoG lies inside the Support Polygon, static equilibrium is possible.
- If the projection reaches the boundary, the robot is at the tipping threshold.
- If the projection lies outside the Support Polygon, static equilibrium cannot be maintained using the existing support contacts alone.

For a hexapod using a Tripod Gait, three supporting feet form a triangular Support Polygon.

### 10.5 Tipping Moment

When the gravity line passes beyond a supporting edge, gravity produces a moment that encourages rotation about that edge.

The magnitude of the moment is:

$$
M_{\mathrm{tipping}}=Wd
$$

Where:

- $W=mg$ is the robot's weight.
- $d$ is the perpendicular distance from the gravity line to the tipping edge.

The closer the CoG projection is to the support boundary, the smaller the static stability margin generally becomes.

### 10.6 Engineering Implications for the Spider Robot

The stability analysis suggests several design considerations:

1. Keep heavy components, particularly the battery, in a suitable position to avoid excessive CoG displacement.
2. Consider the support polygon generated by the selected gait.
3. Ensure that the CoG projection remains within the support polygon during static support.
4. Evaluate the stability margin rather than considering only whether the robot is theoretically balanced.
5. Consider dynamic effects separately when the robot accelerates, decelerates or changes gait.

The static Support Polygon method is a useful initial stability assessment, but it does not fully describe dynamic locomotion.

---

# 11. Overall Design Considerations

The ground contact analysis provides several considerations for the spider foot and leg design:

- Foot geometry should provide sufficient contact area without unnecessary mass.
- Contact pressure should be assessed using realistic supporting-leg loads.
- Curved feet may require Hertzian contact analysis.
- Flat feet can be assessed using average pressure and eccentric loading models.
- Eccentricity should be considered when evaluating non-uniform pressure and loss of full contact.
- CoG position and Support Polygon geometry should be considered together when evaluating stability.

# 12. Limitations and Further Work

The current analysis is primarily theoretical and uses simplified contact assumptions.

The following information is required before a final quantitative design assessment:

- Actual foot geometry and contact dimensions.
- Robot total mass and component mass distribution.
- Supporting-leg configuration and gait.
- Foot and ground material properties.
- Actual contact surface condition.
- Realistic load distribution between supporting legs.

Once these parameters are confirmed, the theoretical models can be used to estimate contact forces, pressure distribution, contact stress and static stability.

The results should be checked against the final CAD geometry and, where appropriate, physical testing or numerical simulation.
