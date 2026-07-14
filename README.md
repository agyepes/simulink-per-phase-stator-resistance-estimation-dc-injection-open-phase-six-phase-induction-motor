# Supplementary files for paper "Per-Phase Stator-Resistance Estimation by DC-Signal Injection in Open-Phase Fault-Tolerant Six-Phase Induction Motor Drives"

This repository contains the open-access Simulink model associated with the method proposed in the following paper:

> A. G. Yepes, M. S. Abdel-Majeed, W. E. Abdel-Azim, M. G. Abdel-Moneim, A. S. Abdel-Khalik, S. Ahmed, and J. Doval-Gandoy, "Per-Phase Stator-Resistance Estimation by DC-Signal Injection in Open-Phase Fault-Tolerant Six-Phase Induction Motor Drives," *IEEE Transactions on Industrial Electronics*, vol. 72, no. 2, pp. 1101–1112, February 2025, [doi:10.1109/TIE.2024.3417992](https://doi.org/10.1109/TIE.2024.3417992).

The model implements the proposed dc-signal-injection method for estimating the individual stator phase resistances of a symmetrical six-phase induction-motor drive in either healthy or open-phase-fault conditions. It includes the machine and control parameters used in most of the experimental tests reported in the paper.

The paper PDF is not part of this repository.

## Contents

| File | Description |
| --- | --- |
| `Simulation.slx` | Self-contained Simulink implementation of the proposed method, including the six-phase machine, current control, dc-injection sequence, per-phase resistance estimation, and healthy/open-phase-fault selection. |
| `README.md` | Description, requirements, usage instructions, provenance, integrity information, and related resources. |
| `LICENSE.txt` | Creative Commons Attribution 4.0 International license notice and attribution information. |
| `CITATION.cff` | Machine-readable software and associated-paper citation metadata. |

## Requirements and compatibility

- MATLAB
- Simulink
- The Specialized Power Systems block library supplied with a compatible MathWorks power-systems product

`Simulation.slx` was saved with MATLAB/Simulink R2018a. Its model metadata identifies the required physical-modeling product as `Power_System_Blocks`.

The unchanged model was load-tested successfully in MATLAB/Simulink R2026a. It cannot be compiled or simulated there without conversion because MathWorks removed the Specialized Power Systems library in R2026a. Use R2018a or another compatible MATLAB release that still provides this library. For R2026a or later, convert the model with MathWorks' `spsConversionAssistant` and validate the converted model before relying on its results.

## How to use

1. Download or clone the repository.
2. Set the repository folder as the current MATLAB folder.
3. Open `Simulation.slx` in a compatible MATLAB/Simulink release.
4. At the top level of the model, set `1: Healthy / 0: OPF` to `1` for healthy operation or `0` for the modeled open-phase-fault case.
5. Adjust the visible operating-point inputs if desired. The supplied values are an initial and reference speed of 500 rpm and a load torque of 7.5 N·m.
6. Run the model. The supplied simulation stop time is 10 s, and the dc-injection trigger begins after a 2 s delay.

The initialization callback defines the vector-space-decomposition transformation, a control sampling period of 100 µs, and the six-phase induction-machine parameters. No separate MAT file or MATLAB script is required.

## Provenance and metadata correction

`Simulation.slx` is byte-for-byte identical to the model in:

- the original final supplementary archive retained with the paper source files; and
- the corrected [supplementary archive currently shared on ResearchGate](https://www.researchgate.net/publication/381293163).

The original retained archive contained a `README.txt` with outdated authorship metadata: it lists M. S. Hamad, who is not an author of this paper. The corrected ResearchGate archive and this repository replace that text file with `README.md`, `LICENSE.txt`, and `CITATION.cff` while leaving `Simulation.slx` unchanged.

### SHA-256 checksum

| File | SHA-256 |
| --- | --- |
| `Simulation.slx` | `69f25bb1578789200e902a2c7905ed1f6632d147a8232e26d2a9fc750100b097` |

For reference, the original final supplementary ZIP retained with the paper source files—and the byte-identical original archive previously shared on ResearchGate—has SHA-256 `ca7cb5657e9ff385be2966bcd9d5647864c655512e2ba28d1f7aebddd7bda328`.

## Related resources

- Paper: https://doi.org/10.1109/TIE.2024.3417992
- Zenodo software record: https://doi.org/10.5281/zenodo.21349688
- IEEE Xplore paper and supplementary-material page: https://ieeexplore.ieee.org/document/10605588/media
- ResearchGate paper record: https://www.researchgate.net/publication/381293072
- ResearchGate supplementary-material record: https://www.researchgate.net/publication/381293163
- Related Simulink tutorial: https://www.youtube.com/watch?v=amyEkhyCE1A

## License

Unless otherwise stated, the files in this repository are licensed under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0). See `LICENSE.txt` for details.

## Citation

Please cite the associated IEEE Transactions on Industrial Electronics paper above when using these files. When citing this archived software release, use https://doi.org/10.5281/zenodo.21349688. A machine-readable citation is provided in `CITATION.cff`.
