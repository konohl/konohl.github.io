Fe14Ni41 Gupta energy landscape — downloadable data
==================================================

Units
  Energies in the XYZ comment lines are in eV.
  Barriers in the transition-state XYZ comment lines are in kcal/mol,
  using 1 eV = 23.06054783 kcal/mol.
  Coordinates are Cartesian, in angstrom.

Composition
  55 atoms (second Mackay-icosahedron magic size), Fe14Ni41: the closest
  55-atom composition to awaruite Ni3Fe (25.5 at.% Fe).

Geometries
  All XYZ coordinates are Gupta-potential stationary points from ABCluster
  and ASE climbing-image NEB. They are NOT PBE-relaxed.

  Fe14Ni41_minima_connected.xyz
    The 34 connected minima, sorted by Gupta energy. The global minimum
    (uid 0) has energy -190.16403867 eV. Each comment line gives the energy,
    uid, and family code/name.

  Fe14Ni41_minima_all_unique.xyz
    All 1000 unique Gupta minima (the 34 connected ones plus 966
    unconnected isolates). This is not the connected set used in the
    landscape figures.

  Fe14Ni41_transition_states.xyz
    The 106 clean transition-state geometries that join two connected
    minima. A saddle is clean if it converged, has exactly one negative
    Hessian mode, and satisfies E_TS >= max(E_start, E_end) - 1e-4 eV.
    Each comment line gives the TS tag, the two endpoint uids, E_TS in eV,
    and both barriers in kcal/mol (from the lower and the higher endpoint).
    Barriers from the lower minimum in this set range from 12.96 to 327.61 kcal/mol.

  Fe14Ni41_connections.csv
    One row per clean transition state: endpoint uids and families, endpoint
    and TS energies (eV), both barriers (kcal/mol), NEB pass, endpoint RMSD.

Gaussian 16 inputs (Fe14Ni41_gjf.zip)
  One .gjf file per connected minimum (minima/) and per clean TS (ts/).
  These are PBEPBE / Stuttgart RSC 1997 ECP single-point jobs built from
  the same SPC template as Fe4Ni9 (GEN PSEUDO=READ, UltraFine integrals,
  SCF=(XQC,Tight,MaxCycle=1024) Guess=Mix 5D 7F), charge 0, multiplicity 71.
  The multiplicity is NOT from a spin scan: it scales the Fe4Ni9 choice
  (19, i.e. 18 unpaired = 4 x 3 + 9 x 0.67) to 14 x 3 + 41 x 0.67 = 69.3,
  rounded to the nearest allowed even count (70). Check it with a spin scan.
  They are single points, not optimizations. The geometries inside are
  the same Gupta coordinates as in the XYZ files, not PBE-relaxed.

Figures
  Fe14Ni41_connectivity_circular.pdf  — circular connectivity by family (3 families)
  Fe14Ni41_disconnectivity.pdf        — disconnectivity graph of the
                                      34 connected minima
