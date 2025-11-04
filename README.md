# Mass-Radius-relationship-of-Neutron-star
===================================================================

Overview
--------
This MATLAB project computes the Mass-Radius (M–R) relation of a neutron star using the Tolman–Oppenheimer–Volkoff (TOV) equations. The M–R relation provides deep insight into the stability, structure, and upper mass limits of neutron stars governed by general relativity.

By varying the central pressure of the neutron star, the code integrates the TOV equations to determine the total gravitational mass and corresponding radius for each configuration. The resulting curve reveals the maximum stable mass and illustrates how compactness changes with increasing central density.

Physics Background
------------------
The TOV equations describe the balance between gravitational collapse and internal pressure in relativistic stars:

    dp/dr = -G * (E + P/c^2) * (M + 4πr^3P/c^2) / (r^2 * (1 - 2GM/rc^2))
    dM/dr = 4πr^2 * E

Here, E is the energy density, P is the pressure, and M is the enclosed mass at radius r. The equations are solved numerically for various central pressures to map the mass-radius relationship.

Features
--------
- Solves the TOV equations for a range of central pressures.
- Produces the Mass-Radius curve of a neutron star.
- Identifies the maximum stable mass and its corresponding radius.
- Uses high-precision numerical integration (ode23s with tight tolerances).

Code Structure
--------------
neutron_star_mass_radius.m
    tov_eqs()     → Defines the relativistic TOV equations.
    Main loop     → Iterates over central pressures and integrates using ode23s.
    Data handling → Identifies the stellar surface (P → 0) and stores radius & mass.
    Plotting      → Generates the M–R curve and marks the maximum mass point.

How to Run
----------
1. Open MATLAB.
2. Place the file neutron_star_mass_radius.m in your working directory.
3. Run:
       neutron_star_mass_radius
4. The code will print the maximum neutron star mass and radius in the command window 
   and plot the M–R relation.

Output
------
- A plot of **Mass (M☉)** vs **Radius (km)**.
- A red marker showing the point of maximum stable mass.
- A dashed vertical line indicating the radius corresponding to maximum mass.
- Example printed output:
      Maximum Mass: 1.934 Solar Mass at Radius 11.532 km

Interpretation
--------------
The M–R curve demonstrates that as the central pressure increases, the star’s mass initially rises, reaches a peak (maximum mass), 
and then decreases for higher pressures — indicating instability against collapse. The point of maximum mass represents the 
limit beyond which no stable neutron star can exist, marking the onset of black hole formation.

Parameters Used
---------------
alpha  = 1.476 km          (Schwarzschild radius per solar mass)
beta   = 0.03778 km^-3     (Density scaling factor)
Anr    = 2.4216
Ar     = 2.8663
n      = 5/3               (Polytropic index)
p0     = logspace(-30, 0)  (Range of central pressures)

Requirements
------------
- MATLAB R2020a or later
- Basic understanding of the TOV equations and numerical ODE solvers

Author
------
Trisha Khan

Developed as part of Astrophysics Masters Thesis

GitHub: https://github.com/Trisha-Khan

Description: MATLAB-based numerical integration of the Tolman–Oppenheimer–Volkoff (TOV) equations to compute the Mass–Radius relation of neutron stars, identifying the maximum stable configuration and exploring general relativistic effects on stellar structure.
