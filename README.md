# pyEUGEN
Simple python version of EUGEN program, as described by Izgorodina et al. (DOI: 10.1021/cg900656z).

INPUT FILE: See 'input.txt' for example of input file (a single input file is used for all three scripts, see below). First row contains the unit cell axes in Å, second line contains angles alpha, beta, gamma in degrees, third row is a convergence condition (not yet implemented), row 4 to end are atom positions within the unit cell, in the format of 'atom_symbol x y z charge'. A single space should separate all the content in the input file. Example file(s) are for the structures of NaCl and CaF2.

## Uploaded scripts are three python notebooks:

1. 'pyEUGEN_dipole_test.ipynb' - tests input file for dipole moment of unit cell contents. If non-zero (net result > 0.0000 D), use pyEUGENE_Harrison to calculate the Madelung potential of the structure.
2. 'PyEUGEN.ipynb' - calculates Madelung potential for structure with zero dipole moment, as described by Izgorodina et al.
3. 'pyEUGEN_Harrison' - calculation of Madelung potential for structures with non-zero dipole moment of the unit cell contents. Uses an expanding sphere of radius 'r' with dummy atom at 'r' with equal but opposite charge as sphere used for Madelung potential calculation. Procedure as described by Izgorodina et al., as originally described by Harrison (DOI: 10.1103/PhysRevB.73.212103).

The input file need to be specified in each notebook. Additionally, the expansion cycles need to be changed as necessary for 2 and 3. Typically 20 - 40 cycles is enough for 3, whereas 2 converges quicker (10-20).
