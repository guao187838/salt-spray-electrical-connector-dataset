# Data Dictionary

| Column | Meaning |
|---|---|
| `metric` | Degradation metric name: `contact_resistance`, `insulation_resistance`, or `corrosion_area`. |
| `specimen_id` | Anonymous specimen identifier. |
| `series_id` | Anonymous measurement series identifier. It does not expose the original measurement position. |
| `stress_level_percent` | Salt spray concentration in percent units, e.g. `0.5` means 0.5%. |
| `stress_level_fraction` | Salt spray concentration as a fraction, e.g. `0.005` means 0.5%. |
| `time_label` | Original time-point label from the spreadsheet, such as `T0` or `T7`. |
| `time_h` | Test time in hours. |
| `processed_value` | Processed degradation indicator. Larger values indicate more severe degradation. |

## Metric Notes

- Contact resistance is reported as change from the initial value in milliohms.
- Insulation resistance is reported as log10-scale loss from the initial value.
- Corrosion area is reported as change from the initial area ratio in percentage points.
