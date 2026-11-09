# TDEE

Food database for TDEE (Total Daily Energy Expenditure) tracking.

## `foods.json`

A list of food items with per-serving nutrition facts. Each entry:

| Field | Description |
|-------|-------------|
| `id` | Unique slug |
| `name` | Name (Thai) |
| `name_en` | Name (English) |
| `serving` | Serving size (`amount`, `unit`, `ml`) |
| `nutrition` | `calories_kcal`, `protein_g`, `fat_g`, `saturated_fat_g`, `carbs_g`, `fiber_g`, `sugar_g` |
| `notes` | Extra notes |

## `boditrax.json`

Body-composition scan history exported from Boditrax. Structure:

| Field | Description |
|-------|-------------|
| `profile` | Account details (`email`, `name`, `date_of_birth`, `gender`, `height_cm`, `recent_clothes_weight_kg`) |
| `source` | Original export filename |
| `exported_at` | Export date |
| `units` | Units for the metric values |
| `latest_scan_date` | Date of the most recent scan |
| `scan_count` | Number of scans |
| `scans` | Scans, **most recent first**. Each has `date`, `datetime`, and a `metrics` map |

Metric keys mirror Boditrax's `BodyMetricTypeId`s in `snake_case` (e.g. `body_weight`,
`fat_mass`, `muscle_mass`, `visceral_fat_rating`, `boditrax_score`). `basal_metabolic_rate_kj`
is the raw value; `basal_metabolic_rate_kcal` is derived (`kJ / 4.184`) for TDEE use.
