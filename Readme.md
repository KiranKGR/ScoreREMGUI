# ScoreREM: A user friendly Matlab-GUI for rapid eye movement (REM) sleep microstructure (Phasic/Tonic) annotation and quantification

**Licence:**  
ScoreREM Copyright (C) 2024 Kiran K G Ravindran. Refer to the License.txt for more details.

## Overview

ScoreREM is a user-friendly Matlab GUI that allows rapid annotation and quantification of rapid eye movement (REM) sleep microstructure. It allows import of sleep polysomnography recordings collected in EDF format, automatically score the hypnogram and REM events. These recordings can range from full polysomnography recordings to partial polysomnography recordings with a minimum of one electroencephalography, electrooculography and electromyography signals available. Legacy cassette recordings and R&K hypnograms are also supported by the application. Custom recording start times can be set using a text file containing markers. Additional channels derivations can be created. Users can choose the segmentation length for scoring the events and filtering options and view the data in the GUI. The application allows the user to loop through REM epochs, score the micro segments as Phasic/Tonic/Artefact, edit the existing sleep scoring and export the scored labels and summary measures for further analysis. The application can also be used for general-purpose scoring of epoch micro segments in other sleep stages as well.

## Requirements and Installation

- **ScoreREM Matlab:** 2023b or newer with signal processing toolbox to allow scoring and export of the labels and analysis results.
- The automatic sleep staging and REM event detection is facilitated via Python language interpreter in Matlab and requires compatible Python 3.11.6 installation and supporting packages (YASA and MNE).
- *The app allows manual scoring in the absense of the python installation*

The application can be installed using the .mlappinstall file in src.

We have provided a [**standalone version of ScoreREM**](https://github.com/KiranKGR/ScoreREMGUI/tree/2ee7f8c4e502ad681c1b462a68c1353d61cdbf46/src/Standalone_App_for_redistribution) which works with the Matlab runtime.

We have provided the supporting documentation to help with the installation. To install Python 3.11.6 and the required packages, read the instructions in [installation support](https://github.com/KiranKGR/ScoreREMGUI/blob/844bc3dde1d610b587019d80b22d538676e47f47/installation_support/Installation_support.md).

The application requires 24 inch screen or over to display correctly.

Please refer to the documentation (Supplemental Materials of the citation below) and citation below for more details.

## Example Data

The example templates for the Marker and hypnograms txt files can be found in [examplefiles](https://github.com/KiranKGR/ScoreREMGUI/tree/b506ea61ac68232449824155ee6347addf1230a7/examplefiles). Public repositories containing example EDF data for exploring the application can be found here:

1. [Haaglanden Medisch Centrum sleep staging database](https://physionet.org/content/hmc-sleep-staging/1.1/)
2. [Sleep-EDF Database Cassette PSG](https://www.physionet.org/content/sleep-edf/1.0.0/)

## Acknowledgements
This work was supported by the UK Dementia Research Institute, [award number UKDRI-7005], through UK DRI Ltd, principally funded by the UK Medical Research Council, and additional funding partner Alzheimer’s Society. The authors thank Dr Valeria Jaramillo, Dr Sara Wong, Giuseppe Atzori, and Marta Messina Pineda for their helpful feedback during software development and testing of the ScoreREM for user acceptability.

## Citation

For any use of ScoreREM please cite:

K. K. G Ravindran and D.-J. Dijk, “ScoreREM: A user-friendly Matlab-GUI for rapid eye movement (REM) sleep microstructure (Phasic/Tonic) annotation and quantification,” SoftwareX, vol. 29, p. 101988, Feb. 2025, doi: [10.1016/j.softx.2024.101988.](https://doi.org/10.1016/j.softx.2024.101988)

## For general in-text referencing guidelines for softwares: 
Katz DS, Chue Hong NP, Clark T et al. Recognizing the value of software: a software citation guide [version 2; peer review: 2 approved]. F1000Research 2021, 9:1257 (https://doi.org/10.12688/f1000research.26932.2)
