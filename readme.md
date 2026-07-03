EU Carbon Flows and Policy Coverage — Master's Thesis
This repository contains the Python code and data files used to construct the carbon flow analyses and visualisations presented in the master's thesis Mapping EU Carbon Policy: A Carbon Flow Analysis and Policy Alignment Assessment of EU Carbon Governance? (Charlotte Westenberg, TU Delft, 2026).


Repository Structure
├── 00data/
│   ├── raw/              # Original datasets as downloaded from Eurostat, EEA, and FAOSTAT
│   ├── fromexcel/        # CSV files exported from the Carbon Flow Calculations Excel workbook
│   ├── processed/        # Cleaned and harmonised data files ready for analysis
│   └── sankey_files/     # Structured CSV input files used to generate Sankey diagrams
├── 01notebooks/
│   ├── data_cleaning.ipynb          # Data harmonisation and unit conversion to tonnes of carbon
│   ├── mass_balance_check.ipynb     # Mass balance verification across all carbon flow categories
│   ├── sankey_visualisations.ipynb  # Sankey diagram generation for individual flow categories
│   ├── combined_sankey_flows.ipynb  # Combined carbon flow Sankey diagram across all categories
│   └── policy_visuals.ipynb         # Policy coverage and alignment visualisations
└── 02outputs/
    └── *.png                        # Final figures as they appear in the thesis


Notebooks
- data_cleaning.ipynb — Loads raw datasets from Eurostat, applies carbon content factors for gas flows to convert physical quantities to tonnes of carbon, and exports processed CSV files for use in subsequent notebooks. Most calculations were not done in Python, but in Excel, and can be found in the supplementary Excel files.
- mass_balance_check.ipynb — Verifies mass balance consistency for fossil carbon, checking that total inflows equal total outflows plus stock changes within acceptable margins. Other mass balance checks were done in the supplementary Excel files.
- sankey_visualisations.ipynb — Generates individual Sankey diagrams for fossil, biogenic, mineral, and goods-embedded carbon flows using Plotly. Flow bands are coloured by energy carrier and outputs are exported as PNG files.
- combined_sankey_flows.ipynb — Integrates all four carbon flow categories into a single combined Sankey diagram representing the full EU carbon economy in 2023, and overlays policies to determine policy coverage. This notebook includes the governed versus ungoverned carbon flow Sankey diagrams.
- policy_visuals.ipynb — Generates policy coverage visualisations and policy instrument distribution charts presented in Chapter 7.

Data Sources
Raw data were downloaded in March 2026 from the following sources:
- Eurostat — Energy balances (NRG_CB_OIL, NRG_CB_GAS, NRG_CB_SFF, NRG_BAL_CB), material flow accounts (ENV_AC_MFA), waste statistics (ENV_WASGEN, ENV_WASTRT), wood removals (FOR_REMOV), mineral production (ds-059358), EU trade (ds-045409)
- European Environment Agency — Greenhouse gas inventory (EUA_CRT_2023)
- FAOSTAT — Food balances (Food Balances 2010–)

For full dataset details and carbon content factors, see the Carbon Flow Calculations Excel workbook available at: https://repository.tudelft.nl/

Requirements
The notebooks were developed using Python 3.13. The following packages are required:
pandas
plotly
jupyter

Install dependencies using:
bashpip install pandas plotly jupyter

Supplementary Materials
This repository accompanies two Excel workbooks:

Carbon Flow Calculations — raw data, conversion calculations, and mass balance tables: https://repository.tudelft.nl/
Policy Analysis — full coded policy dataset including long list, core list, and exclusion rationales: https://repository.tudelft.nl/

Contact
For questions about the data or methodology, please open an issue in this repository.