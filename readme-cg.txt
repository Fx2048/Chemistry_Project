==========
 Contents
==========

em.mdp                   --- MDP file for Energy Minimising the CG System
1000ns.mdp               --- MDP file for 1000 ns of Molecular Dynamics
xxxx-coarsegrain.pdb     --- PDB file of the system
coarsegrain.top          --- Topology File for system
coarsegrain.ndx          --- Index file for system
martini_v2.2.itp         --- Martini Parameters 
protein-cg.itp           --- Protein Parameters 

================
 Example Usage 
================

Energy Minimise:

mkdir EM

gmx grompp -f mdp_files/em.mdp -o EM/em -c xxxx-coarsegrain.pdb -n coarsegrain.ndx -p coarsegrain.top -maxwarn -1

cd EM

gmx mdrun -deffnm em -v

=========================================================================================================

Run 1000 ns of Coarse Grained Molecular Dynamics Simulation:

mkdir 1000ns

gmx grompp -f mdp_files/1000ns.mdp -o 1000ns/md -c EM/em.gro -n coarsegrain.ndx -p coarsegrain.top -maxwarn -1

cd 1000ns

gmx mdrun -deffnm md -v

=========================================================================================================
