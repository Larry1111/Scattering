# Classical Chaotic Scattering
This respository includes the simulation of classical chaotic scattering, specifically the Gaspard-Rice system and Rutherford scattering. 
## Introduction
Classical chaotic scattering is a type of scattering where no quantum effect is involved, and the system shows strong sensitivity to initial condition. The setup of  Gaspard-Rice system includes a point particle colliding elastically with three hard disks arranged in the shape of an equilateral triangle. Rutherford scattering entails scattering between charged particles. 
## Installation
The programming language is Python

Then, open terminal and type
```pip install VPython```

## Code 
For source code and explanation, see folders [Hard Particles Scattering](https://github.com/Larry1111/Scattering/tree/main/Hard%20Particles%20Scattering) and [Rutherford Scattering](https://github.com/Larry1111/Scattering/tree/main/Rutherford%20Scattering).
## Results
![Gaspard Scattering](Figures/Gaspard_sim.png "Gaspard scattering")![Gaspard Plot](Figures/Gaspard_plot3.png "Gaspard plot")
![Rutherford Scattering](Figures/Rutherford_scattering.png "Rutherford scattering")![Rutherford Plot](Figures/Rutherford_plot.png "Rutherford plot")

## Discussion
The results from the simulation of Gaspard-Rice system were comparable to the standard results from early publications. However, as the plot was zoomed in, the plot started to deviate dramatically from the standard plot. The inaccuracy might be due to the insufficient data size since 100000 datapoints were used in [1], but only 2500 data points were used in figure 1b. Furthermore, the code could still be more efficient as several hours were required to generate plots with more data points, and the dt variable for which the movements of the particles depend on might also cause inaccuracy in the trajectory of the particles as they bounce off from the hard disks. 
## Conclusion
In this respository, a basic program simulating Gaspard Rice system and Rutherford scattering was demonstrated. The sensitivity of classical chaotic scattering to initial conditions such as impact parameter, number, and location of the barriers was explored. As shown in figure 1b and figure 2b, some regions show smooth behavior, while others show chaotic behavior. The chaotic regions demonstrate the strong sensitivity of the scattering angle to the initial impact parameter. Further considerations for this repository include modifying the code to generate a more accurate blowup of the Gaspard Rice plot and experimenting with different configurations for both Gaspard Rice system and Rutherford scattering.

## Citation
[1] : https://aip.scitation.org/doi/pdf/10.1063/1.168549

[2] : https://dournac.org/info/chaotic_scattering



