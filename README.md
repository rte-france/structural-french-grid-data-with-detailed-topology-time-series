# Dataset Description


## Download files via Git
To download files via git clone, you should first install git-lfs.

## /!\ 202502 Download issue - explaination /!\
Since the release of this dataset, we have been experiencing a high volume of git clones. Therefore, we will stop using LFS (a naturally paid solution on GitHub as it consumes bandwidth and storage on their end).

In the meantime, if you would like access to a few individual files, you can contact [Boris Dolley](https://fr.linkedin.com/in/boris-dolley-rte) via private message on LinkedIn.

## Introduction

This dataset offers a series of snapshots of the French transmission electricity network in *node-breaker* topology, with a temporal granularity of **5 minutes**, covering the period from **2021 to 2023**. Only the structure and topology of the grid is described, there is no information on injections and power flows. The snapshots are provided in compressed **[xiidm](https://powsybl.readthedocs.io/projects/powsybl-core/en/stable/grid_exchange_formats/iidm/index.html)** format. 

## Dataset Content

Each network file includes the following details:

- **Substations**: Detailed information on electrical substations, with the topology in *node-breaker* format.
- **Switches**: Description of disconnectors and other switching devices (position and connection status).
- **Lines and tranformers** : Information on the static characteristics of transmission lines and transformers, including thermal limits. Power flows are not displayed.
- **Loads**: Location of loads (consumption) on the netwro and their connection status. Injections are not displayed.
- **Generators**: Information on electrical generators regarding their location, energy type, connection status and static data such as min/max active power limits. Injections are not displayed.
- **Other Elements**: Includes other essential components of the electrical network (phase-shifter transformers, HVDC lines, HVDC converter station, shunts, capacitors, batteries...).

The identifiers of the network elements are **consistent over time**, ensuring traceability and coherence throughout the covered period. However, in the event of maintenance or structural modifications to the network, changes to the identifiers may occur.

## Data Format

- **Format**: The data are provided in **[xiidm](https://powsybl.readthedocs.io/projects/powsybl-core/en/stable/grid_exchange_formats/iidm/index.html)** format (bzip2 compressed).
- **Compatibility**: The snapshots are readable with **[pypowsybl](https://github.com/powsybl/pypowsybl)** (or **[PowSyBl](https://powsybl.org)**, allowing for easy manipulation and analysis of the electrical network. Python notebooks are available on **[GitHub](https://github.com/powsybl/pypowsybl-notebooks)** to help you manipulate the data.
- **Temporal Granularity**: Snapshots every **5 minutes**, enabling fine-grained analysis of grid topology evolutions (one file each 5 minutes).
- **Spatial perimeter**: All structural grid components of the French transmission network are represented from 63 kV to 400 kV voltage levels. Interconnection lines with neighboring countries are modeled as dangling lines.

## Limitations

- **Power flows and injections Not Included**: The data do not contain power flows or injections. Only the structural and topological information of the network is available. In order to compute power flows, injection reconstruction is necessary using open-source agregated data. A reconstruction methodology has been proposed by [M. Chatzos](https://www.linkedin.com/in/minas-chatzos-b90164164), [M. Tanneau](https://www.linkedin.com/in/mathieu-tanneau-47937ba9) and [P. Van Hentenryck](https://www.linkedin.com/in/pascal-van-hentenryck-50a5741) in "[Data-driven time series reconstruction for modern power systems research](https://arxiv.org/abs/2110.13772)" (Electric Power Systems Research, 2022). Then, power flows can be computed using traditional simulation tools.

## Potential Uses

This dataset is ideal for developing **optimization and AI models for grid topology optimization** and power flow control, as it is representative of the real variability of grid topology.

## Remarks

- **ID Changes**: Users should be aware of potential ID changes due to maintenance or structural modifications.
- **List of open-source injection data**:
  - Eco2mix - Real-time electricity data in France : https://www.rte-france.com/en/eco2mix
  - Actual generation by generating unit : https://data.rte-france.com/catalog/-/api/generation/Actual-Generation/v1.1 
  - ENTSO-E Transparency platform - Cross-border physical flows : https://transparency.entsoe.eu/transmission-domain/physicalFlow/show
 
## Roadmap

- 20241220: Publication of the first 2 months (2021, January and Febuary)
- 20250330: Publication of the total dataset (2021, 2022 and 2023 = 36 months)

## Authors

- [Selim Ben Turkia](https://fr.linkedin.com/in/selim-ben-turkia-b78614223): Developper for crunching and cleaning the data from the source database
- [Camille Pache](https://fr.linkedin.com/in/camille-pache-289bba60): Manager of the publication project
- [Boris Dolley](https://fr.linkedin.com/in/boris-dolley-rte): Github publisher for public dataset
- [Lucas Saludjian](https://fr.linkedin.com/in/lucas-saludjian-8438181b0): Scientific advisor
- [Patick Panciatici](https://fr.linkedin.com/in/patrick-panciatici-a8a09858): Senior scientific advisor



