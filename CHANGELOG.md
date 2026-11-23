# Changelog

All notable changes to this project are listed here. Versions follow [Semantic Versioning](https://semver.org/).

## [1.0.0] – 2026-11-23

First public release.

### Added
- Batch analysis of up to 100 CIF structures: network dimensionality, interpenetration, SBUs, metal coordination, ligands, hydrogen bonds, π–π stacking and porosity.
- Sortable tables with CSV, TSV and XLSX export; 15 figures as SVG/PNG; 3D viewer with PNG/SVG/MP4 export; Word (.docx) report.
- Version number shown in the header and exported by the analysis core.
- Example CIF files (`examples/`) and automated tests (`tests/`).

### Fixed
- Bond-angle variance σ² of square-planar CN 4 sites (τ₄ < 0.5) is now measured against 90° over the four cis angles; before, it used the tetrahedral angle and gave σ² ≈ 2300°² for a perfect square plane. Quadratic elongation is no longer reported for flat CN 4 polyhedra (it was infinite).
- Channel dimensionality of the void: all distinct translations are now reduced, not only the first 400, which could under-report 3D channels as 2D.

- SBU description: periodic 2D and 3D SBUs are now called "inorganic layer (2D)" and "inorganic framework (3D)" instead of "rod (2D, )" and "rod (3D, )".

### Changed
- Removed code left over from the Borophosphate Polyhedra Lab that this program never called (framework-polyhedra and organic-template routines).
- `hullVolume` now computes the polyhedron volume once instead of twice.
- The empty structure list no longer refers to built-in examples; it points to the `examples/` folder.
