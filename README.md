# FinalProject_250_Lily
Final Project for Computational Physics 25000 - Fall 2019


Simulation of water droplet evaporation
I have a 2D NxN matrix of molecules for a simplified water droplet model. I will assume the molecules are evaporating from the outer layer inwards. A molecule needs to absorb enough energy to overcome vapor pressure and break its hydrogen bonds to then escape into the surrounding air as a gas. To simplify the system, I am going to ignore vapor pressure and focus on hydrogen bonds. At the beginning of the simulation I will have to input a temperature. Molecules at the edge of a droplet evaporate first, so I will iterate through the cells around the edge of my matrix until they evaporate. I will assume the Maxwell-Boltzmann distribution applies. I will use this distribution to randomly obtain a velocity for my molecule. I will use this velocity to calculate the kinetic energy of my molecule. If the kinetic energy is bigger than the hydrogen bond energy, the molecule breaks free and I remove it from my matrix.

Pseudocode:

Input temperature

Create matrix NxN filled with 1s (to represent a present molecule, 0 for evaporated)

Iterate around the cells at the edge

Obtain the velocity of this molecule: use rejection sampling to obtain a random velocity from the Maxwell-Boltzmann distribution

Calculate the kinetic energy of the molecule E_k=(1/2)mv^2

If (kinetic energy)>(hydrogen bond energy): molecule evaporates => set cell =0

Run again
