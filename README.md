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
