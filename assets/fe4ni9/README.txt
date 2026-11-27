Fe4Ni9 Gupta energy landscape — downloadable data
================================================

Units
  Energies in the XYZ comment lines are in eV.
  Barriers in the transition-state XYZ comment lines are in kcal/mol,
  using 1 eV = 23.06054783 kcal/mol.
  Coordinates are Cartesian, in angstrom.

Geometries
  All XYZ coordinates are Gupta-potential stationary points from ABCluster
  and ASE climbing-image NEB. They are NOT PBE-relaxed.

  Fe4Ni9_minima_connected.xyz
    The 186 connected minima, sorted by Gupta energy. The global minimum
    (uid 0) has energy -37.48847853 eV. Each comment line gives the energy,
    uid, and family code/name.

  Fe4Ni9_minima_all_unique.xyz
    All 1000 unique Gupta minima (the 186 connected ones plus 814
    unconnected isolates). This is not the connected set used in the
    landscape figures.

  Fe4Ni9_transition_states.xyz
    The 270 clean transition-state geometries. A saddle is clean if it
    converged, has exactly one negative Hessian mode, and satisfies
    E_TS >= max(E_start, E_end) - 1e-4 eV. Each comment line gives the
    TS tag, the two endpoint uids, E_TS in eV, and both barriers in
    kcal/mol (from the lower and the higher endpoint). Barriers from the
    lower minimum in this set range from 0.53 to 104.52 kcal/mol.

Gaussian 16 inputs (Fe4Ni9_gjf.zip)
  One .gjf file per connected minimum (minima/) and per clean TS (ts/).
  These are PBEPBE / Stuttgart RSC 1997 ECP single-point jobs at charge
  and multiplicity 0,19, built from the SPC template (GEN PSEUDO=READ,
  UltraFine integrals, SCF=(XQC,Tight,MaxCycle=1024) Guess=Mix 5D 7F).
  They are single points, not optimizations. The geometries inside are
  the same Gupta coordinates as in the XYZ files, not PBE-relaxed.

Figures
  Fe4Ni9_connectivity_circular.pdf  — circular connectivity by family
  Fe4Ni9_disconnectivity.pdf        — disconnectivity graph of the
                                      186 connected minima
