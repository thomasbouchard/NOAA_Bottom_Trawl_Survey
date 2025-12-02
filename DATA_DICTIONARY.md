# Data Dictionary

This dictionary provides variable definitions, data structures, and lookup tables for all datasets used in this project.

**Location:** 
**Author:** Thomas Bouchard
**Last Updated:** 2025-12-2

## Table of Contents
1. [Dataset Index] (#dataset-index)
2. [Dataset Level Dictionaries] (#dataset-level-dictionaries)
  - Cruise Data
  - Tow / Tow Effort Data
  - Biological Data
  - Support Tables

## Dataset Index

| File | Description |
|------|-------------|
| `22561_SVDBS_CRUISES.csv` | Cruise-level metadata for NEFSC bottom trawl surveys. |
| `22561_UNION_FSCS_SVBIO.csv` | Joined FSCS/SVDBS biological observations at tow/species level. |
| `22561_UNION_FSCS_SVCAT.csv` | Catch number and weight of each species by tow. |
| `22561_UNION_FSCS_SVLEN.csv` | Length-frequency measurements by tow and species. |
| `22561_UNION_FSCS_SVSTA.csv` | Tow / station-level effort and environmental data. |
| `support_tables\SVDBS_CLOUD.csv` | Cloud Coverage Coding % Clear - 0-9. |
| `support_tables\SVDBS_MATURITY_CODES.csv` | Maturity Coding - D,E,I,R,S,T,U,X. |
| `support_tables\SVDBS_SEX_CODES.csv` | Sex Coding - 0-2, 0-5 for American Lobster, 0-7 for Northern Shrimp. |
| `support_tables\SVDBS_SVGEAR.csv` | Survey Gear Coding - description of gear used. |
| `support_tables\SVDBS_SVMSTRATA.csv` | Defines spacial strata used including location, description, and number of tows. |
| `support_tables\SVDBS_SVSPECIES_LIST.csv` | Species Coding including Sci. Name, Common Name, and SVSPP. |
| `support_tables\SVDBS_SVVESSEL.csv` | Vessel's and their abbreviations - occassional vessel info. |
| `support_tables\SVDBS_WEATHER.csv` | Weather Coding 0-9, 99. |
| `support_tables\SVDBS_XBT.csv` | XBT 'Instrument Used' Coding (Expendable BathyThermograph). |


## Dataset-Level Dictionaries

### `22561_SVDBS_CRUISES.csv`

**Description:** Cruise-level metadata for NEFSC bottom trawl surveys.

| Column | Type | Missing % | # Unique | Example | Description |
|--------|------|-----------|----------|---------|-------------|
| `CRUISE6` | int64 | 0.0 | 58 | `196803` | TODO |
| `PURPOSE_CODE` | int64 | 0.0 | 1 | `10` | TODO |
| `PURPOSE` | object | 0.0 | 1 | `NMFS NEFSC BOTTOM TRAWL SURVEY` | TODO |
| `STATUS_CODE` | int64 | 0.0 | 1 | `10` | TODO |
| `STATUS` | object | 0.0 | 1 | `Audited` | TODO |
| `SEASON` | object | 0.0 | 1 | `SPRING` | TODO |
| `YEAR` | int64 | 0.0 | 58 | `1968` | TODO |

---

### `22561_UNION_FSCS_SVBIO.csv`

**Description:** Joined FSCS/SVDBS biological observations at tow/species level.

| Column | Type | Missing % | # Unique | Example | Description |
|--------|------|-----------|----------|---------|-------------|
| `CRUISE6` | int64 | 0.0 | 29 | `196803` | TODO |
| `CRUISE` | int64 | 0.0 | 46 | `6803` | TODO |
| `STRATUM` | int64 | 0.0 | 150 | `1050` | TODO |
| `TOW` | int64 | 0.0 | 37 | `3` | TODO |
| `STATION` | int64 | 0.0 | 629 | `1` | TODO |
| `STATUS_CODE` | int64 | 0.0 | 1 | `10` | TODO |
| `ID` | int64 | 0.0 | 8398 | `196803010500030001` | TODO |
| `SVSPP` | int64 | 0.0 | 51 | `105` | TODO |
| `CATCHSEX` | float64 | 100.0 | 0 | `None` | TODO |
| `INDID` | float64 | 75.9 | 80 | `1.0` | TODO |
| `LENGTH` | float64 | 0.0 | 138 | `33.0` | TODO |
| `INDWT` | float64 | 77.5 | 2192 | `0.323` | TODO |
| `SEX` | object | 0.3 | 9 | `1.0` | TODO |
| `MATURITY` | object | 20.6 | 14 | `X` | TODO |
| `AGE` | float64 | 13.4 | 50 | `3.0` | TODO |
| `AGE_DATA_FLAG` | object | 0.0 | 1 | ` ` | TODO |
| `STOM_VOLUME` | float64 | 100.0 | 0 | `None` | TODO |
| `STOM_WGT` | float64 | 100.0 | 0 | `None` | TODO |
| `IND_FISH_COMMENTS` | object | 0.0 | 1 | ` ` | TODO |

---

### `22561_UNION_FSCS_SVCAT.csv`

**Description:** Catch category / summary weights by tow.

| Column | Type | Missing % | # Unique | Example | Description |
|--------|------|-----------|----------|---------|-------------|
| `CRUISE6` | int64 | 0.0 | 45 | `196803` | Cruise Identifier |
| `CRUISE` | int64 | 0.0 | 63 | `6803` | Cruise Identifier |
| `STRATUM` | int64 | 0.0 | 154 | `1050` | Spatial Stratum assoc. with the tow -- Keys to SVDBS_SVMSTRATA |
| `TOW` | int64 | 0.0 | 38 | `3` | Tow ID within that stratum |
| `STATION` | int64 | 0.0 | 661 | `1` | Location within a stratum where 1 tow attempt occurs |
| `STATUS_CODE` | int64 | 0.0 | 1 | `10` | Status of tow - valid, partial, aborted, failed |
| `ID` | int64 | 0.0 | 15596 | `196803010500030001` | ID for catch created from CRUISE6,CRUISE,STRATUM,TOW,STATION |
| `SVSPP` | int64 | 0.0 | 501 | `23` | Species identifier -- Keys to SVDBS_SVSPECIES_LIST  |
| `CATCHSEX` | int64 | 0.0 | 6 | `0` | Sex of catch |
| `EXPCATCHNUM` | float64 | 0.8 | 2323 | `8.0` | TODO |
| `EXPCATCHWT` | float64 | 0.0 | 11338 | `20.0` | TODO |
| `SCIENTIFIC_NAME` | object | 0.0 | 503 | `Leucoraja ocellata (winter skate)` | Scientific name of catch |
| `CATCH_COMMENT` | object | 29.4 | 946 | ` ` | Comments related to catch |

---

### `22561_UNION_FSCS_SVLEN.csv`

**Description:** Length-frequency measurements by tow and species.

| Column | Type | Missing % | # Unique | Example | Description |
|--------|------|-----------|----------|---------|-------------|
| `CRUISE6` | int64 | 0.0 | 11 | `196803` | TODO |
| `CRUISE` | int64 | 0.0 | 19 | `6803` | TODO |
| `STRATUM` | int64 | 0.0 | 109 | `1050` | TODO |
| `TOW` | int64 | 0.0 | 38 | `3` | TODO |
| `STATION` | int64 | 0.0 | 485 | `1` | TODO |
| `STATUS_CODE` | int64 | 0.0 | 1 | `10` | TODO |
| `ID` | int64 | 0.0 | 3271 | `196803010500030001` | TODO |
| `SVSPP` | int64 | 0.0 | 229 | `23` | TODO |
| `CATCHSEX` | float64 | 0.1 | 3 | `0.0` | TODO |
| `LENGTH` | float64 | 0.0 | 457 | `49.0` | TODO |
| `EXPNUMLEN` | int64 | 0.0 | 638 | `1` | TODO |
| `SCIENTIFIC_NAME` | object | 0.0 | 231 | `Leucoraja ocellata (winter skate)` | TODO |
| `LENGTH_COMMENT` | object | 0.0 | 1 | ` ` | TODO |

---

### `22561_UNION_FSCS_SVSTA.csv`

_Could not read file automatically: 'utf-8' codec can't decode byte 0xb1 in position 16943: invalid start byte_

---

### `support_tables\SVDBS_CLOUD.csv`

**Description:** TODO – add dataset description.

| Column | Type | Missing % | # Unique | Example | Description |
|--------|------|-----------|----------|---------|-------------|
| `cloud` | int64 | 0.0 | 10 | `0.0` | TODO |
| `pctclear` | float64 | 8.3 | 11 | `0.0` | TODO |
| `doe` | float64 | 100.0 | 0 | `nan` | TODO |
| `doc` | float64 | 100.0 | 0 | `nan` | TODO |
| `uoe` | float64 | 100.0 | 0 | `nan` | TODO |
| `uoc` | float64 | 100.0 | 0 | `nan` | TODO |

---

### `support_tables\SVDBS_MATURITY_CODES.csv`

**Description:** TODO – add dataset description.

| Column | Type | Missing % | # Unique | Example | Description |
|--------|------|-----------|----------|---------|-------------|
| `maturity` | object | 0.0 | 8 | `D` | TODO |
| `maturity_description` | object | 0.0 | 8 | `Developing` | TODO |

---

### `support_tables\SVDBS_SEX_CODES.csv`

**Description:** TODO – add dataset description.

| Column | Type | Missing % | # Unique | Example | Description |
|--------|------|-----------|----------|---------|-------------|
| `sex` | int64 | 0.0 | 8 | `0` | TODO |
| `sex_description` | object | 0.0 | 8 | `Unsexed, unknown, or sex not observed...` | TODO |

---

### `support_tables\SVDBS_SVGEAR.csv`

**Description:** TODO – add dataset description.

| Column | Type | Missing % | # Unique | Example | Description |
|--------|------|-----------|----------|---------|-------------|
| `svgear` | int64 | 0.0 | 76 | `0` | TODO |
| `gear_definition` | object | 0.0 | 75 | `Plankton, Hydrographic and/or Misc Ge...` | TODO |
| `doe` | object | 0.0 | 21 | `10/7/2001 4:18:56 PM` | TODO |
| `doc` | object | 84.2 | 12 | `8/9/1999 3:30:06 PM` | TODO |
| `uoe` | object | 0.0 | 2 | `SVDBS` | TODO |
| `uoc` | object | 84.2 | 4 | `HYACHMET` | TODO |

---

### `support_tables\SVDBS_SVMSTRATA.csv`

**Description:** TODO – add dataset description.

| Column | Type | Missing % | # Unique | Example | Description |
|--------|------|-----------|----------|---------|-------------|
| `strgrp_desc` | object | 0.0 | 9 | `OFFSHORE REGULAR` | TODO |
| `stratum` | int64 | 0.0 | 369 | `1010` | TODO |
| `stratum_name` | object | 0.0 | 85 | `SNE HUDSON CANYN` | TODO |
| `stratum_area` | float64 | 0.5 | 281 | `2516.0` | TODO |
| `midlat` | float64 | 17.9 | 220 | `4008.0` | TODO |
| `midlon` | float64 | 17.6 | 234 | `7307.0` | TODO |
| `minlat` | float64 | 0.3 | 215 | `3928.0` | TODO |
| `maxlat` | float64 | 1.6 | 218 | `4046.0` | TODO |
| `minlon` | float64 | 1.4 | 250 | `7216.0` | TODO |
| `maxlon` | float64 | 0.3 | 261 | `7351.0` | TODO |
| `blocks` | float64 | 54.2 | 115 | `620.0` | TODO |
| `notows` | float64 | 54.7 | 12 | `1.0` | TODO |
| `doe` | float64 | 100.0 | 0 | `None` | TODO |
| `doc` | float64 | 100.0 | 0 | `None` | TODO |
| `uoe` | float64 | 100.0 | 0 | `None` | TODO |
| `uoc` | float64 | 100.0 | 0 | `None` | TODO |

---

### `support_tables\SVDBS_SVSPECIES_LIST.csv`

_Could not read file automatically: Error tokenizing data. C error: Expected 3 fields in line 168, saw 5
_

---

### `support_tables\SVDBS_SVVESSEL.csv`

**Description:** TODO – add dataset description.

| Column | Type | Missing % | # Unique | Example | Description |
|--------|------|-----------|----------|---------|-------------|
| `vessel_name` | object | 0.0 | 287 | `ABEL-J` | TODO |
| `vessel_abbrev` | object | 0.3 | 286 | `AJ` | TODO |
| `country_of_origin` | object | 93.0 | 3 | `USA` | TODO |
| `home_port` | object | 93.4 | 17 | `Woods Hole, MA` | TODO |
| `agency_name` | object | 97.2 | 8 | `NMFS-NEFSC` | TODO |
| `length_overall_ft` | float64 | 95.8 | 12 | `176.0` | TODO |
| `construction` | object | 97.9 | 3 | `FIBERGLASS` | TODO |
| `year_built` | object | 96.9 | 8 | `1963` | TODO |

---

### `support_tables\SVDBS_WEATHER.csv`

**Description:** TODO – add dataset description.

| Column | Type | Missing % | # Unique | Example | Description |
|--------|------|-----------|----------|---------|-------------|
| `weather` | int64 | 0.0 | 11 | `0` | TODO |
| `weather_def` | object | 0.0 | 11 | `Clear (No clouds at any level)` | TODO |
| `doe` | float64 | 100.0 | 0 | `None` | TODO |
| `doc` | float64 | 100.0 | 0 | `None` | TODO |
| `uoe` | float64 | 100.0 | 0 | `None` | TODO |
| `uoc` | float64 | 100.0 | 0 | `None` | TODO |

---

### `support_tables\SVDBS_XBT.csv`

**Description:** TODO – add dataset description.

| Column | Type | Missing % | # Unique | Example | Description |
|--------|------|-----------|----------|---------|-------------|
| `xbt` | int64 | 0.0 | 9 | `0` | TODO |
| `xbt_def` | object | 0.0 | 9 | `No temperature data recorded` | TODO |
| `doe` | float64 | 100.0 | 0 | `None` | TODO |
| `doc` | float64 | 100.0 | 0 | `None` | TODO |
| `uoe` | float64 | 100.0 | 0 | `None` | TODO |
| `uoc` | float64 | 100.0 | 0 | `None` | TODO |

