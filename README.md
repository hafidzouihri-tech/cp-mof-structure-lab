# Coordination Polymer & MOF Structure Lab

[![tests](https://github.com/hafidzouihri-tech/cp-mof-structure-lab/actions/workflows/tests.yml/badge.svg)](https://github.com/hafidzouihri-tech/cp-mof-structure-lab/actions/workflows/tests.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
<!-- After the first Zenodo release, paste its DOI badge here -->

**Batch structural analysis of metal–organic complexes, coordination polymers and metal–organic frameworks (MOFs) from CIF files, entirely in the web browser.**

The program is a single, self-contained HTML file. It needs no installation, no server, no internet connection and no external libraries. CIF files never leave the user's computer.

**Live version:** `https://hafidzouihri-tech.github.io/cp-mof-structure-lab/` (after GitHub Pages is enabled)

---

## What it computes

For a series of up to 100 crystal structures (multi-block CIFs accepted):

| Area | Results |
|---|---|
| **Network** | Dimensionality of each bonded component (0D complex, 1D chain [uvw], 2D layer (hkl), 3D framework), degree of interpenetration, guests and counter-ions |
| **SBUs** | Metal clusters and rods joined by μ-donor atoms or three-atom bridges (O–C–O, N–N, N–C–N), M···M distances, node connectivity (input for ToposPro / Systre) |
| **Metal centres** | CN, donor set, M–L bond lengths, Baur distortion index, bond-angle variance σ², quadratic elongation, ECoN, τ₄ / τ₄′ / τ₅, continuous shape measures for CN 2–9 with shape maps and minimal-distortion paths, bond-valence sums |
| **Ligands** | Formula and tentative name (bdc, btc, bpy, phen, im, OAc, tu, DMF …), denticity κ, bridging μ, chelate ring sizes, carboxylate modes in Harris notation (x.y₁y₂, syn/anti), linker role |
| **Interactions** | D–H···A hydrogen bonds, π–π stacking (Cg···Cg, α, β, slippage) |
| **Porosity** | Empty and probe-accessible volume, largest included sphere (LCD), channel dimensionality, crystal density |

### Outputs

- Sortable tables, exportable as CSV, as tab-separated text or as one multi-sheet **XLSX** workbook.
- 15 publication-style **figures** (SVG, or PNG at 300–1200 dpi).
- An interactive **3D viewer**: polyhedra, labels, symmetry codes, distances and angles, click-to-measure. Views export as PNG/SVG, and 360° rotations record as **MP4** video.
- A complete **Word report** (.docx): methods with editable Word equations, tables, written result paragraphs, figures and numbered references.

## Quick start

1. Download `index.html`, or open the live version.
2. Open it in a recent Chrome, Edge, Firefox or Safari.
3. Drop CIF files on the upload area (try the files in [`examples/`](examples/)).
4. Press **Run analysis** and browse the tabs.

The full guide is in [`docs/user-guide.md`](docs/user-guide.md). The algorithms and equations are described in [`docs/methods.md`](docs/methods.md).

## Repository layout

```
index.html              the application (HTML + CSS + JavaScript, no dependencies)
examples/               test CIF files with known answers
tests/                  automated tests of the analysis core (Node.js, no dependencies)
docs/                   user guide and description of methods
CITATION.cff            how to cite this software
.zenodo.json            metadata for the Zenodo archive (DOI)
.github/workflows/      continuous integration (runs the tests on every push)
```

## Running the tests

The tests load the analysis code directly from `index.html`, so they check exactly what the browser runs. Node.js 18 or newer is required; nothing else needs installing.

```bash
npm test
# or
node --test tests/core.test.js
```

## Limitations

- Reference polyhedra for CN 7–9 are idealised geometries, so S values for these CNs are approximate. Use SHAPE when exact values are needed.
- Topology is reduced to node connectivity. Full net symbols (e.g. **pcu**, **dia**) need ToposPro or Systre.
- Porosity is computed on a grid (0.5 Å by default). Volumes depend on grid spacing, probe radius and van der Waals radii.
- Bonds are assigned from distance cut-offs. Check the cut-offs for unusual metals or long secondary contacts.

## How to cite

If you use this program in published work, please cite it as given in [`CITATION.cff`](CITATION.cff). GitHub's "Cite this repository" button shows the citation in APA and BibTeX.

## Contributing and support

Bug reports and suggestions are welcome as [GitHub issues](https://github.com/hafidzouihri-tech/cp-mof-structure-lab/issues). Please attach the CIF that shows the problem, if you can share it. See [`CONTRIBUTING.md`](CONTRIBUTING.md).

## License

MIT. See [`LICENSE`](LICENSE).
