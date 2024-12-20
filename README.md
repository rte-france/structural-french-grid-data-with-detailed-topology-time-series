# Dataset Description

## Introduction

This dataset offers a series of snapshots of the French transmission electricity network in *node-breaker* topology, with a temporal granularity of **5 minutes**, covering the period from **2021 to 2023**. Only the structure and topology of the grid is described, there is no information on injections and power flows. The snapshots are provided in compressed **xiidm** format. 

## Dataset Content

Each network file includes the following details:

- **Substations**: Detailed information on electrical substations, with the topology in *node-breaker* format.
- **Switches**: Description of disconnectors and other switching devices.
- **Lines and tranformers** : Information on the characteristics of transmission lines and transformers, including thermal limits.
- **Loads**: Data related to loads (consumption) connected to the network.
- **Generators**: Information on electrical generators.
- **Other Elements**: Includes other essential components of the electrical network.

The identifiers of the network elements are **consistent over time**, ensuring traceability and coherence throughout the covered period. However, in the event of maintenance or structural modifications to the network, changes to the identifiers may occur.

## Data Format

- **Format**: The data are provided in **xiidm** format.
- **Compatibility**: The snapshots are readable with **pypowsybl** (or **PowSyBl**), allowing for easy manipulation and analysis of the electrical network.
- **Temporal Granularity**: Snapshots every **5 minutes**, enabling fine-grained analysis of grid topology evolutions.
- **Spatial perimeter**: All structural grid components of the French transmission network are represented from 63 kV to 400 kV voltage levels. Interconnection lines with neighboring countries are modeled as dangling lines.

## Limitations

- **Power flows and injections Not Included**: The data do not contain power flows or injections. Only the structural and topological information of the network is available. In order to compute power flows, injection reconstruction is necessary using open-source agregated data. A reconstruction methodology has been proposed by M. Chatzos, M. Tanneau and P. Van Hentenryck in "Data-driven time series reconstruction for modern power systems research" (Electric Power Systems Research, 2022). Then, power flows can be computed using traditional simulation tools.

## Potential Uses

This dataset is ideal for developing **optimization and AI models for grid topology optimization** and power flow control, as it is representative of the real variability of grid topology.

## Remarks

- **ID Changes**: Users should be aware of potential ID changes due to maintenance or structural modifications.
- **List of open-source injection data**:
  - Eco2mix - Real-time electricity data in France : https://www.rte-france.com/en/eco2mix
  - Actual generation by generating unit : https://data.rte-france.com/catalog/-/api/generation/Actual-Generation/v1.1 
  - ENTSO-E Transparency platform - Cross-border physical flows : https://transparency.entsoe.eu/transmission-domain/physicalFlow/show
  
## Authors

- Selim Ben Turkia: developper for crunching and cleaning datas from the source database
- Camille Pache: manager of this publication project 
- Boris Dolley: publication of the public dataset

## Roadmap

- 20241220: Publication of the first 2 months (2021, January and Febuary)
- 20250330: Publication of the total dataset (2021, 2022 and 2023 = 36 months)
- ...
