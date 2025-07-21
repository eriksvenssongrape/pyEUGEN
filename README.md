# pyEUGENE
Modified python version of the EUGEN program, as described by Izgorodina et al. (DOI: 10.1021/cg900656z).

INPUT FILE: See 'input.txt' for example of input file (a single input file is used for all three scripts, see below). First row contains the unit cell axes in Å, second line contains angles alpha, beta, gamma in degrees, third row is a convergence condition (not yet implemented), row 4 to end are positions of ions within the unit cell, in the format of 'atom_symbol x y z charge'. A single space separates all the content in the input file. Example file(s) are for the structures of NaCl and CaF2.

Calculation of the Madelung constant is done with respect to the first atom in the list. To cycle through all crystallographically unique atoms, simply move the atom in question the top of the ion list and run the script again.

## Uploaded scripts are three python notebooks:

**1**. 'pyEUGENE_dipole_test.ipynb' - tests input file for dipole moment of unit cell contents. If non-zero (net result > 0.0000 D), use pyEUGEN_Harrison to calculate the Madelung potential of the structure, rather than pyEUGEN.

**2**. 'PyEUGENE.ipynb' - calculates Madelung constant for structure with zero dipole moment, as described by Izgorodina et al.

**3**. 'pyEUGENE_Harrison' - calculation of Madelung potential for structures with non-zero dipole moment of the unit cell contents. Uses an expanding sphere of radius 'r' with dummy atom at 'r' with equal but opposite charge as sphere used for Madelung potential calculation. Procedure as described by Izgorodina et al., as originally described by Harrison (DOI: 10.1103/PhysRevB.73.212103).

The input file need to be specified in each notebook. Additionally, the expansion cycles need to be changed as necessary for **2** and **3**. Typically 20 - 40 cycles is needed for **3**, whereas **2** converges quicker (10-20).
