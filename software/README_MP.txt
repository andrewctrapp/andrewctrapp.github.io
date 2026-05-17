===
These are instructions for using C++ code and mathematical programming techniques to identify diverse optima and near-optima, infused with a single quality notion, for binary integer optimization problems.

The code implements the ideas outlined in the manuscript by Thierry Petit and Andy Trapp entitled "Enriching Solutions to Combinatorial Problems via Solution Engineering," published in the INFORMS Journal on Computing.

The code was written by Andy Trapp, Ph.D. (Worcester Polytechnic Institute), in collaboration with Dr. Thierry Petit, and was last edited on 2019/1/1.
===

1) This project requires the IBM ILOG CPLEX Studio and its associated callable library.

2) There are two zip files. The MP_Code.zip file contains a .cpp file, a .hpp file, and a makefile, while the Test_Instances.zip file contains test instances.

3) The makefile must be configured to point to the correct directory where CPLEX is installed.

4) The C++ code is currently customized to solve Generalized Assignment Problem (GAP) instances. These are presently specified in the C++ code (around line 137). As of January 1, 2019, the instances we use are available online at http://people.brunel.ac.uk/~mastjjb/jeb/orlib/ -- additional instances must be created in the same format, and placed in the same directory as the .cpp and .hpp files.

5) We make available several GAP instances that were specified in the manuscript.