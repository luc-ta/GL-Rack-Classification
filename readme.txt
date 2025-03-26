#====================================================================
# Library of all GL-racks of order 1 to 8 up to isomorphism
# Compiled by Lực Ta
# Based on the rack library of Petr Vojtěchovský and Seung Yeop Yang at 
#    https://www.cs.du.edu/~petr/libraries_of_algebraic_structures.html
# For more information, see the following paper:
#    link
#====================================================================

#====================================================================
# INSTALLATION AND USAGE:
# 1) copy the data files
#       GL_racks_of_order_n.txt (for n in [1..13])
#    into some folder.
# 2) replace 'path' below with a path to the folder containing
#    the above files (should end with /)
# 3) start GAP
# 4) read this file into GAP
# 5) to construct the kth GL-rack of order n, call
#       GLR.Rack(n, k);
#    to display it in the form (R, u, d), where R is a list of 
#    length n, and R[i] = s_i for all 1 \leq i \leq n
# 6) to search for all GL-racks of order n, 1) download and set up the
#    library of Vojtěchovský and Yang, 2) change n and k to the
#    appropriate quantities in gl-rack-tester.txt (n = rack order,
#    k = number of racks of order n, and 3) run
# ReadAsFunction(Concatenation(GLR.path, "gl-rack-tester.txt"))();
# 7) to search for GL-quandles and medial GL-racks of order n, 1) change
#    n and k to the appropriate quantities in gl-quandle-medial-tester.txt
#    and 2) run
# ReadAsFunction(Concatenation(GLR.path, "gl-quandle-medial-tester.txt"))();
# 8) to compare R-coloring numbers for two Legendrian knots, 1)
#    duplicate one of the sample coloring files in the same folder
#    as the above files, 2) in that file, set local variables 
#    y1, ..., ym where m is the maximum over the number of strands
#    between the two front projections and change n, k1, and k2
#    depending on which/how many GL-racks you'd like to test, 
#    3) replace the sample crossing relations with those of the 
#    two front projections, and 4) run
# ReadAsFunction(Concatenation(GLR.path, "name.txt"))();
#    where 'name' is the name of the file you created
# 9) to view the numbers of GL-racks of each order, see enumeration.xlsx
#====================================================================

# global variable holding all data, methods, etc., for the library
GLR := rec();

# replace 'path' with a path to the folder containing data files (should end with /)
GLR.path := "path";

GLR.Rack := function(n, k)
    local localRacks;
    localRacks:=ReadAsFunction(Concatenation(GLR.path, "GL_racks_of_order_", String(n), ".txt"))();
    return localRacks[k];
end;
