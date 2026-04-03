Current 
==
## Structure schema

| No. | Column Name                                                                                              |
| --- | -------------------------------------------------------------------------------------------------------- |
| 1   | datapoint_id                                                                                             |
| 2   | id                                                                                                       |
| 3   | exact_polymer_name                                                                                       |
| 4   | Polymer Family                                                                                           |
| 5   | Chemical Structure                                                                                       |
| 6   | Repeating Unit Formula                                                                                   |
| 7   | Molecular Weight of the Repeating Unit (g/mol)                                                           |
| 8   | Molecular Weight - (polymer molecular weight/repeat-unit molecular weight) (Number of repeated monomers) |
| 9   | Mw (Molecular Weight) [kDa]                                                                              |
| 10  | PDI (Polydispersity Index)                                                                               |
| 11  | carrier_type                                                                                             |
|     |                                                                                                          |
## Processing and doping schema
| No. | Column Name                           |
| --- | ------------------------------------- |
| 1   | Film Method Preparation               |
| 2   | Dopant                                |
| 3   | Doping Level (Solution Concentration) |
| 4   | Doping Temperature                    |
| 5   | units_doping_level                    |
## Performance schema
| No. | Column Name             |
| --- | ----------------------- |
| 1   | seebeck_coefficient     |
| 2   | electrical_conductivity |
| 3   | power_factor_Extracted  |
| 4   | ZT                      |
| 5   | Temperature             |
| 6   | power_factor_Calculated |
| 7   | ZT_Calculated           |
## Graph and extracted data schema
| No. | Column Name                      |
| --- | -------------------------------- |
| 1   | graph_variable [Y vs X] [Type 1] |
| 2   | doping_or_oxidation_level        |
| 3   | graph_variable [Y vs X] [Type 2] |
| 4   | doping_or_oxidation_level        |
| 5   | graph_variable [Y vs X] [Type 3] |
| 6   | doping_or_oxidation_level        |
| 7   | graph_variable [Y vs X] [Type 4] |
| 8   | graph_variable [Y vs X] [Type 5] |
| 9   | seebeck_coefficient              |
| 10  | electrical_conductivity          |
| 11  | graph_variable [Y vs X] [Type 6] |
| 12  | power_factor_Extracted           |
| 13  | electrical_conductivity          |
| 14  | graph_type                       |
| 15  | digitization_method              |
## Reference and provenance schema
| No. | Column Name       |
| --- | ----------------- |
| 1   | reference_doi     |
| 2   | evidence_location |