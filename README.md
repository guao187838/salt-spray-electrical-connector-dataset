# Salt Spray Degradation Dataset for Electrical Connectors

This repository contains anonymized and processed degradation indicators from salt spray accelerated life tests of electrical connectors. Original absolute measurements are not included.

The dataset supports the associated manuscript entitled "Salt-Spray Corrosion Failure Analysis and Mechanism-Informed Remaining Useful Life Assessment of Electrical Connectors".

## Data Files

- `data/contact_resistance_processed.csv`: processed contact-resistance degradation indicators.
- `data/insulation_resistance_processed.csv`: processed insulation-resistance degradation indicators.
- `data/corrosion_area_processed.csv`: processed corrosion-area degradation indicators.
- `data/all_metrics_processed_long.csv`: combined long-format table for the three processed degradation metrics.
- `data/dataset_summary.csv`: row counts, time ranges, and processed-value ranges by metric and stress level.

## Processing

Only processed degradation indicators are released:

- Contact resistance: current contact resistance minus the initial value of the same measurement series.
- Insulation resistance: `log10(initial resistance) - log10(current resistance)` for the same measurement series.
- Corrosion area: `(current area ratio - initial area ratio) * 100`, reported as percentage-point change.

Under this convention, larger processed values indicate more severe degradation.
Small negative values may appear because measurements can fluctuate around the initial state.

## Failure Criteria

In the associated study, functional failure criteria were applied to the original absolute measurements before data release:

- Contact resistance: failure is identified when the contact resistance increases to twice its initial steady value or exceeds 5 milliohms.
- Insulation resistance: failure is identified when the insulation resistance decreases below 1000 megaohms.
- Corrosion area: failure is identified when the corrosion area ratio reaches the criterion used in the corresponding experiment or analysis.

The released CSV files contain only processed degradation indicators, so these absolute criteria should not be applied directly to the CSV values. In particular, the released insulation-resistance value is `log10(initial resistance) - log10(current resistance)`, not resistance in ohms. Converting the 1000 megaohm criterion into the released scale would require the initial resistance of each measurement series, which is not included.

Original absolute measurements, per-series initial values, and per-series converted thresholds are not included. Therefore, the released data are intended for degradation-trend analysis, method demonstration, and comparative modeling on processed indicators, while pseudo-life labels and failure-threshold calculations in the paper were generated internally from the original absolute measurements.

## Test Conditions

The stress variable is salt spray concentration. The released stress levels are 0.5%, 1%, 2%, 3%, 4%, and 5%.

Sampling time nodes are provided explicitly in `time_h`.

- 0.5% and 1%: 0, 24, 48, 72, 96, 120, 144, 168 h.
- 2% and 3%: 0, 12, 24, 36, 48, 60, 72, 84, 96, 108, 120 h.
- 4% and 5%: 0, 12, 24, 36, 48, 60, 72, 84, 96 h.

## Anonymization

Original specimen labels were replaced with sequential anonymous identifiers such as `specimen_001`. The released files contain processed degradation indicators only. Original absolute measurements, model code, pseudo-life labels, trained model outputs, and prediction results are not included.

## Suggested Citation

Please cite the related paper or dataset record when using this dataset. See `CITATION.cff`.

Associated manuscript:

Gu, A., Jiang, C., Qi, Y., and Suo, B. Salt-Spray Corrosion Failure Analysis and Mechanism-Informed Remaining Useful Life Assessment of Electrical Connectors.

## Repository

Public repository: https://github.com/guao187838/salt-spray-electrical-connector-dataset

## Supplementary Material

The accompanying failure-mechanism analysis is available as
[`supplementary_material.pdf`](supplementary_material/supplementary_material.pdf).

## License

Dataset contents are released under CC BY 4.0. See `LICENSE`.
