# Minimal de-identified dataset — LTFU and mortality in TB cohort

This repository contains the minimal de-identified dataset accompanying the manuscript:

> **"Causal effect of loss to follow-up on mortality in a population-based tuberculosis cohort in Brazil"** (submitted to *PLOS Medicine*, 2026).

It is provided to satisfy the journal's data availability requirement and to support independent verification and re-analysis.

## Files

| File | Size | Description |
|---|---|---|
| `minimal_dataset.csv` | 39 MB | Main dataset — 171,048 individuals × 32 variables |
| `minimal_dataset.csv.gz` | 4 MB | Gzip-compressed version of the same dataset |

## De-identification

The following potentially-identifying information has been removed or transformed:

- The personal identifier (`sinan_clean`) is **replaced** by a sequential anonymous `id` (1 … 171,048).
- All exact dates (treatment start, treatment end, date of death) are **removed**. The only calendar-time variable retained is `tx_start_year` (integer year of treatment initiation, 2013–2023).
- All ICD-10 codes for cause of death are **dropped**; only the high-level classification (`cod_class`) is retained.
- No municipality, residence, or geographic identifier is included.
- Time-to-event variables are kept as **durations** (days), which are not identifying.

## Variables (32)

| Variable | Type | Description |
|---|---|---|
| `id` | int | Anonymous sequential identifier |
| `age_tb` | int | Age at TB treatment initiation, years |
| `age_group` | factor | 15–24 / 25–44 / 45–64 / ≥65 |
| `sex` | factor | Male / Female |
| `race_clean` | factor | Black or Mixed / White / Indigenous and Asian |
| `edu_clean` | factor | ≤7 years / 8–11 years / ≥12 years |
| `hiv_aids` | factor | Positive / Negative |
| `diabetes` | factor | Yes / No |
| `other_immuno_condition` | factor | Yes / No |
| `mental_health` | factor | Yes / No |
| `alcohol` | factor | Yes / No |
| `drug_use` | factor | Yes / No |
| `tobacco_use` | factor | Yes / No |
| `homelessness` | factor | Yes / No |
| `incarcerated` | factor | Yes / No |
| `clinical_clean` | factor | Anatomical site (Pulmonary / Extrapulmonary / Both / Missing) |
| `lab_confirmed_stat` | factor | Laboratory-confirmed TB (Yes / No) |
| `diagnosis_setting` | factor | Outpatient / ED-Inpatient / Institution-based ACF / etc. |
| `hosp_admission` | factor | Hospitalization at diagnosis (Yes / No) |
| `dot_status` | factor | Directly observed therapy received (Yes / No) |
| `itt_group` | factor | Exposure: Loss to follow-up / Non-LTFU |
| `time_d_tx` | float | Time from treatment start to death/censoring (days) — primary time origin |
| `time_rn_tx` | float | Time from treatment start to retreatment/censoring (days) |
| `time_d` | float | Time from end-of-treatment-episode to death (days) — for post-disengagement landmarks |
| `time_rn` | float | Time from end-of-treatment-episode to retreatment (days) |
| `event_d` | int | Death event (1 = died during follow-up) |
| `event_rn` | int | Retreatment event (1 = retreatment recorded) |
| `true_tx_duration_yrs` | float | Treatment duration before LTFU (years) — within-LTFU analyses |
| `cod_class` | factor | tb_strict / tb_via_tbweb / non_tb / ntb_via_tbweb / respiratory / hiv_other / unknown |
| `tb_hybrid` | int | TB-attributable death (1) under primary hybrid attribution |
| `nontb_hybrid` | int | Non-TB death (1) under primary hybrid attribution |
| `tx_start_year` | int | Year of treatment initiation (2013–2023) |

## Variables NOT included

- **Drug resistance status (`dr_status`)** — used in subgroup analyses (Appendix §5). Built from a separate phenotypic/molecular DST lookup; not redistributed here.

## License

Released under [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) (public domain dedication).

## Citation

If you use this dataset, please cite the corresponding publication.
