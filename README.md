> **Note**  
> This is a demo. Formal version will be released in the future.  

Environmental kinetic Monte Carlo (EKMC) simualations for the Au@anatase TiO<sub>2</sub>(101) system under CO gas conditions. 

There is a demo that can be executed in linux environment. Compilation environment: GNU Fortran (GCC) 8.5.0 20210514 (Red Hat 8.5.0-18)  

Total_bulk.xyz is a coordinate file that contains a Au bulk supported on TiO<sub>2</sub> substrate. This file defines the lattice space, which is the complete set of all possible lattice points used in the EKMC simulation; periodic doundary conditions will be applied in the x and y directions.  

ini.xyz is a customizable input structure file, which specifies which lattice points in the space are occupied by atoms in the intial structure. Here, the initial structure features a Au nanoparticle of a specific size supported on TiO<sub>2</sub> substrate.  

The temperature and CO pressure can be defined in the file of input.  

During the simulation, the following files will be generated:  

- **atom_str_{00 ... 50}.xyz:**  
 This file captures the structural evolution during the simulation, with a recording inteval of 10,000 steps.  

- **Energy_{00 ... 50}.dat:**  
 This file records the energy information during the simulation, with a recording inteval of 10,000 steps. The data columns represent, in order: 
  1. Number of atomic jumping events
  2. Steps  
  3. Time (in s)  
  4. E<sub>a</sub> for the jump event (if the current step is an atomic jump)  
  5. E<sub>b</sub> for the jump event (if the current step is an atomic  jump)  
  6. E<sub>f</sub> for the jump event (if the current step is an atomic  jump)  
  7. Total system energy  
  8. Total cohesive energy  
  9. Total Au-Au bond energy (the sum of this value and the  previous cohesive energy gives the total Au–Au interaction  energy)  
  10. Total adsorption energy  
  11. Total adhesion energy  

- **step_rec_{00 ... 50}.dat:**  
 This file provides time and event statistics during the simulation, with a recording inteval of 10,000 steps. The data columns represent, in order: 
  1. Time (in s)
  2. Steps
  3. Number of atomic jumping events
  4. Number of CO adsorption events
  5. Number of CO desorption events
  6. Placeholder (0) 
  7. Placeholder (0) 
  8. Number of CO diffusion events
  9. Placeholder (0)  
  10. Placeholder (0)   
- **last_one.xyz:**
 This file provides the final structure. The last column records the state of the site, where 0 represetns an empty surface site, 1 represents a CO-occupied surface site, and 5 means a bulk site. Additionally, the element "C" represents a substrate site. 

