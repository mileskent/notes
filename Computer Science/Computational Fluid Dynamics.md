---
aliases:
  - CFD
---

*Computational Fluid Dynamics* (CFD) is the simulation of the [[Fluid Dynamics|dynamics of fluids]] using Computers, which is useful because we exist in fluids that are dynamic! From Rocketry to Power Plants, when a failure in the field can mean people die, being able to predict how your design will fare is of the utmost importance.
# Governing Equations
In CFD, we use discretize the [[Navier Stokes Equations]] to predict fluid dynamics, meaning we translate the continuous equations into a system of [[Algebraic Equation]]s that a computer can solve. We specifically examine the [[Navier Stokes Equations#Incompressible Navier Stokes Equations]] for simplicity.

![[Navier Stokes Equations]]

# Approaches
There are a variety of approaches to actually carrying out the simulation.
## Eulerian
Imagine standing on a bridge and watching the water flow past. You focus on fixed points in space and track how velocity and pressure change at those specific locations over time.
#todo https://www.montana.edu/mowkes/research/source-codes/GuideToCFD.pdf
## Lagrangian
Imagine being a tiny particle floating in the river. You follow individual "fluid parcels" as they move through space and time.
## Hybrid
### Stable Fluids
![[Stable Fluids]]
