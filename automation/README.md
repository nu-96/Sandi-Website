# Inn From the Storm - Data Automation

Automated data collection for statistics about incarcerated African American women in Missouri.

## Data Collected

This automation collects and organizes data from:

### 1. CDC (Centers for Disease Control)
- HIV/AIDS rates in correctional facilities
- Health disparities for incarcerated women
- Comparison to general population

### 2. Missouri Department of Corrections
- Missouri prison population statistics
- Female incarceration numbers
- Release/reentry statistics
- Racial disparities in Missouri

### 3. Bureau of Justice Statistics (BJS)
- National recidivism rates
- Women's recidivism statistics
- African American women incarceration disparities
- Evidence-based interventions that reduce recidivism

## Installation

```bash
cd automation
npm install
```

## Usage

Collect all data:
```bash
npm run collect
# or
node collect-data.js
```

Collect specific sources:
```bash
npm run collect:cdc      # CDC HIV/AIDS data only
npm run collect:missouri # Missouri DOC data only
npm run collect:bjs      # Bureau of Justice Statistics only
```

## Output

Data is saved to the `data/` folder as JSON files:

```
automation/
├── data/
│   ├── cdc-hiv-aids.json      # CDC health statistics
│   ├── missouri-doc.json       # Missouri corrections data
│   ├── bjs-recidivism.json     # National recidivism data
│   ├── summary.json            # Combined summary
│   └── website-stats.json      # Simple stats for website use
├── collect-data.js
├── package.json
└── README.md
```

## Key Statistics Collected

| Metric | Value | Source |
|--------|-------|--------|
| AA Women Incarceration Rate | 2x higher than white women | Sentencing Project |
| Housing Instability (1st year) | 60%+ | Multiple studies |
| HIV Rate in Prisons | 5x general population | CDC |
| National Recidivism (5yr) | 44% | BJS |
| Education Impact on Recidivism | 43% reduction | RAND |
| Trauma History in Incarcerated Women | 86% | BJS |

## Scheduled Collection

To run this automatically, set up a cron job:

```bash
# Run weekly on Sundays at midnight
0 0 * * 0 cd /path/to/automation && npm run collect
```

Or use GitHub Actions (see `.github/workflows/collect-data.yml` if added).

## Data Sources

- [CDC Correctional Health](https://www.cdc.gov/hiv/group/correctional.html)
- [Missouri DOC](https://doc.mo.gov/)
- [Bureau of Justice Statistics](https://bjs.ojp.gov/)
- [The Sentencing Project](https://www.sentencingproject.org/)
- [Prison Policy Initiative](https://www.prisonpolicy.org/)

## Notes

- Some data is scraped from public websites; availability may change
- Statistics include cached/reference values when live data unavailable
- Run periodically to get updated statistics
- All data is from public, official sources

## License

MIT - Created for Inn From the Storm by Luniero
