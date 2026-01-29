# Ship Database Schema Designer

An interactive web app to visualize and plan database schema transformations for fishing vessel data.

## Features

- **Schema Comparison View**: Visualize the transformation from a flat 185-column CSV to a normalized 14-table relational database
- **Interactive Field Mapping**: Click on any field to see which original columns it replaces
- **Column Designer**: Drag-and-drop interface to create custom table structures
- **Column Statistics**: See fill rates and unique values from the full dataset
- **Export**: Export your schema design as JSON

## Live Demo

Visit: [https://YOUR_USERNAME.github.io/ship-schema-designer/](https://YOUR_USERNAME.github.io/ship-schema-designer/)

## Data Summary

- **Original**: 185 columns, 191,281 vessel records
- **Sample**: 10,000 rows included for demo (full dataset available separately)
- **Proposed Schema**: 14 normalized tables with ~51% column reduction

## Table Types

| Type | Description | Example |
|------|-------------|---------|
| Core | Central entity table | `vessels` |
| Lookup | Reference data (rarely changes) | `authorizing_bodies`, `countries` |
| Junction | Many-to-many relationships | `vessel_authorizations`, `vessel_iuu_listings` |
| Supporting | Additional detail tables | `vessel_name_history`, `vessel_arrests` |

## Local Development

Simply open `index.html` in a browser, or serve locally:

```bash
npx serve -p 3000
```

## Files

- `index.html` - Main application (React + Tailwind CSS)
- `sample_data.csv` - 500 row sample for preview
- `full_data.csv` - 10,000 row sample for statistics
- `team_share_data.csv` - 1,000 row cleaned sample (empty columns removed, "Vessel" → "Ship")
