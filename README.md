spaceMARINE
===========

Solves 2D/3D hydrodynamic problems in Eulerian framework on a Cartesian grid with Adaptive Mesh Refinement via the BoxLib library. The name is an acronym for Space Mesh Adaptive RefINEment to signify that it is an AMR code for astrophysical use; it also happens to be the name of a fighting force from the game Warhammer 40,000.

Usage
-----

Users only need to modify
 - `init_phi.f90` This should be done by writing your own routine using the included `init_template.f90` file and calling it a new name (e.g., `sedov.f90`) and then linking it via `ln -s sedov.f90 init_phi.f90`
 - Adiabatic index `gamma` found in `physics_declarations.f90`; currently it is set at 5/3.
 - Scaling parameters; it is up to the user to ensure the units are consistent (e.g., `pscale = rscale*velscale**2`)
 - Changing Riemann solver in `advance.f90`; currently only set up with Roe & HLLE solvers with plans to add HLLD when MHD is added in
 - Change parameters in `main.f90` related to maximum AMR levels, dimensionality, end time (assumes start time ==  0), number of cells per dimension, high & low lengths (in code units)
   - This will be later done via a Fortran `namelist` file

I cannot recommend using this right now because it's not actually working. Hopefully in the near future it will work.

Collaboration
-------------

I currently am working alone on this side project. If you are interested in working on this, please let me know via email or comment.
