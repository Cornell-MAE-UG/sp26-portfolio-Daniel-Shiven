---
layout: project
title: Beam Nutcracker Project
description: Statics Class Project
technologies: n/a
image: /assets/images/beam_nutcracker.jpeg
---

## Find
Update the nutcracker design by replacing the user-applied grip force with a linear actuator and analyzing the handles as beams. Determine:
- Required actuator force
- Location of maximum elastic deflection
- Beam design (cross-section and material) such that deflection is minimized and below 2% of handle length

## Given
From the original nutcracker design:
- Distance from pin to nut: d1 ≈ 20 mm
- Handle length: d2 ≈ 136 mm
- Required force per jaw: C = 1000 N
- Required actuator force (from moment balance): Fa ≈ 147 N

## Assumptions
- The handle is modeled as a beam with a fixed support at the hinge
- Forces act only in the transverse (vertical) direction
- Beam has constant cross-section
- Material is linear elastic
- Actuator applies force at the end of the handle

## Beam Model

Let:
- L = 136 mm
- a = 20 mm
- Fa = 147 N (downward at x = L)
- C = 1000 N (upward at x = a)

The beam experiences two transverse point loads.

## Bending Moment

For a cut at position x:

For 0 ≤ x < 20 mm:

M(x) = Fa(L − x) − C(a − x)

For 20 ≤ x ≤ 136 mm:

M(x) = Fa(L − x)

## Elastic Curve Equation

EI (d²v/dx²) = M(x)

So:

For 0 ≤ x < 20:

EI (d²v/dx²) = Fa(L − x) − C(a − x)

For 20 ≤ x ≤ 136:

EI (d²v/dx²) = Fa(L − x)

## Maximum Deflection Location

The elastic curve is obtained by integrating the moment equation twice:

EI (d²v/dx²) = M(x)  
dv/dx = θ(x)  
v(x) = deflection  

Since bending moment produces curvature, and curvature is integrated to obtain slope and then displacement, the total deflection accumulates along the beam length.

Although the internal bending moment is largest near the hinge, the slope continues to increase along the beam, leading to the largest displacement at the end of the beam.

Therefore, the maximum deflection occurs at:

x = L = 136 mm

## Deflection Constraint

The problem requires:

δ_max ≤ 0.02L

δ_max ≤ 0.02(136)

δ_max ≤ 2.72 mm

## Beam Design

Use a rectangular cross-section:

I = (b h³) / 12

Selected design:

- Material: 6061 Aluminum  
- Width: b = 15 mm  
- Thickness: h = 8 mm  

Moment of inertia:

I = (15 × 8³) / 12  
I = 640 mm⁴  

Elastic modulus:

E = 69,000 N/mm²  
Therefore:
EI = 69,000 × 640  
EI = 44,160,000 N·mm²  

Increasing thickness significantly improves stiffness due to the cubic dependence of h in the moment of inertia.

## Actuator Selection

Required actuator force:

Fa = 147 N  

Convert to pounds:

Fa ≈ 33.1 lb  

Selected actuator:
- Progressive Automations PA-14 Mini Linear Actuator
- Force rating: 150 lb

Safety factor:

SF = 150 / 33.1 ≈ 4.5  

## Final Design

- Handle length: 136 mm  
- Distance to nut: 20 mm  
- Material: 6061 Aluminum  
- Cross-section: 15 mm × 8 mm  
- Maximum allowable deflection: 2.72 mm  
- Actuator: 150 lb PA-14  

## Discussion

The maximum deflection occurs at the end of the beam due to the cumulative effect of curvature along its length. The selected beam design ensures sufficient stiffness while minimizing material usage, with thickness being the dominant factor in reducing deflection.

The actuator replaces the human grip force and provides sufficient load to achieve the required 1000 N compressive force at the nut. The selected actuator provides a large safety factor, ensuring reliable operation.

Overall, the updated design maintains the original mechanical advantage while improving usability through automated force application.
