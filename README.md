# Project: Dashboard & Data Analysis: Electronic Release Atlas 1990–2000

[English](README.md) | [Spanish](README.es.md)

## Description

In this project for ThePower's Data Analytics bootcamp, I will apply the knowledge acquired in the “Dashboard & Data Analysis” module.

To complete it, I followed the specifications provided in the “Project: Dashboard & Data Analysis” lesson.

## Background

The topic of this project arose from a personal initiative. I have also worked as a DJ and electronic music producer for more than 20 years, which sparked a particular interest in exploring insights from a decade that was crucial to the evolution of this music.

## Project Definition and Objectives

“The expansion of electronic music in the 1990s: styles, labels, formats, demand, and market value.”

How did the production, demand, and ratings of electronic music releases evolve between 1990 and 2000, and which styles, labels, formats, and countries had the greatest presence in the market?

Discogs catalogs releases with information such as artist, label, format, country, year, tracklist, and edition details, allowing a rich analysis from the perspective of collecting, editions, and the physical music market.

This connects the analysis with the evolution of styles such as house, techno, electro, ambient, and downtempo, while showing which labels and countries drove the scene during that decade. Discogs began in 2005 as an electronic music database before expanding its catalog to other genres and formats.

Conduct an exploratory analysis of electronic music releases between 1990 and 2000 and present the main findings in a dashboard.

## Research Questions

The analysis is conceived as a study of electronic music production, demand, and ratings in the 1990s and aims to answer questions such as:

- How did the number of electronic music releases evolve between 1990 and 2000?
- Which styles and subgenres accounted for the most releases?
- Which record labels were the most prolific?
- Which countries published the most releases?
- Which physical format dominated, and how did it evolve?
- Which releases generated the greatest interest among Discogs users?
- What relationship exists between community interest, ratings, and market prices?
- Which artists, labels, and styles stand out in terms of demand, collection ownership, or ratings?
- How did the composition of the electronic music market change throughout the decade?
- Which styles reached the highest market prices?

## Proposed KPIs

- Total releases analyzed [Total Releases].
- Number of releases by year [Releases by year].
- Number of releases by style or subgenre [Selected styles by year].
- Number of releases by format [Formats by year].
- Number of releases by record label [Top 10 record labels by release count].
- Number of releases by country [Releases by country].
- Number of unique artists [Unique Artist Credits].
- Number of unique labels [Unique Labels].
- Total users who own each release (`have`).
- Total users who want each release (`want`).
- Demand ratio: `want / have` [Top 10 highest-rated releases].
- Overall average rating.
- Average rating by style, label, country, or year.
- Median price by style, label, country, or year.
- Release rankings by `have`, `want`, `num_ratings`, and `median_price`.

## Initial Hypotheses

- The number of electronic music releases grew during the first half of the 1990s.
- Vinyl was the dominant format, especially for club- and DJ-oriented releases.
- House, Deep House, Garage House, Techno, and Progressive House accounted for a significant share of releases.
- Certain labels were particularly active, such as Strictly Rhythm, Nervous Records, Network Records, Cutting Records, FFRR, Deconstruction, Positiva, and Perfecto.
- Releases wanted by more users may have higher median prices.
- Average rating may be associated with collection interest, although not necessarily with market price.
- Certain countries, particularly the United States, United Kingdom, Germany, Italy, Netherlands, and France, accounted for a significant share of releases.

These hypotheses will be validated or rejected through exploratory analysis.

## Project Structure

```text
Electronic_release_atlas_1990_2000/
│
├── README.md
│
├── data/
│   ├── raw/
│   │   └── 01_discogs_electronic.csv
│   ├── cleaning/
│   │   └── 02_discogs_electronic_cleaning.xlsx
│   └── processed_analytics_dashboard/
│       └── 03_discogs_electronic_processed_analytics_dashboard.xlsm
│
└── lookandfeel/
    ├── printscreen_dashboard_electronic_release_atlas_1990_2000.png
    └── mockup_dashboard_electronic_release_atlas_1990_2000.jpg
```

## Column Extraction

From the cleaning file `02_discogs_electronic_cleaning.xlsx` to the final file `03_discogs_electronic_processed_analytics_dashboard.xlsm`: I transferred the required columns from `Discogs_electronic_cleaning` to a second worksheet, `Discogs_electronic_processed`, using direct worksheet references and the formula:

```excel
=Discogs_electronic_cleaning1!A:A
```

I then converted the results to static values using Paste Special > Values, so the final database would not depend on formulas or references to the original worksheet, reducing the processing load. This worksheet provides the cleaned releases used by the final file and dashboard.

## Requirements

The project must cover the following:

- Data transformation and cleaning.
- Descriptive data analysis.
- Dashboard.
- Explanatory analysis report.
- Project README.

## Tools

I used Microsoft Excel to complete the project.

## Data

The dataset used was `discogs_electronic.csv`, the Discogs Electronic Music Dataset (1990–2000), available at https://www.kaggle.com/datasets/justinpakzad/discogs-electronic-music-dataset-1990-2000?resource=download

It contains a selection of electronic music releases from 1990 to 2000, mainly vinyl, some CDs, and other formats. It was collected from the marketplace at https://www.discogs.com, the world's largest database and sales platform for music in physical formats. The data was obtained through web scraping using Python and Scrapy.

The dataset covers different subgenres, allowing the study of the production, circulation, and ratings of electronic releases during a key decade for house, techno, garage, trance, and club culture.

Suggestions from the dataset creator:

Rarity and desirability: “Use want/have values to determine which records or styles are rare or more sought-after. Discover which records are popular but not widely available, and whether rarity is linked to artist popularity, style, or release date.”

Geographic influences: “Examine how the electronic music scene varied across countries [country_clean]. Which countries led electronic music production? How did styles vary by region?”

Artist popularity and influence: “Explore which artists were most influential in the 1990s. This could be assessed through num_ratings, average_rating, or the number of people who want/have their records.”

## Analysis Limitations

The dataset comes from scraping and contains duplicates, cataloging errors, or incomplete values.

Discogs is a collaborative database, so metadata quality and completeness may vary between releases.

The dataset represents a sample of electronic music releases, not necessarily all musical production during the period (872,171 releases).

Presence on Discogs does not necessarily equal sales, commercial popularity, radio airplay, or streams.

Prices reflect market information at a specific point in time and may be influenced by rarity, media condition, edition, collector demand, and current availability.

## Main Dataset Characteristics

- Period analyzed: 1990–2000.
- Main genre: electronic music.
- Columns: 15 in the original dataset and 19 in the final dataset.
- Records: 32,542 in the original dataset and 29,926 after cleaning.
- Physical formats: mainly vinyl, with CDs and other media also represented.

## Original Data Dictionary

| Column | Data type | Description |
|---|---|---|
| `artist` | Text | Main artist or group on the release. |
| `title` | Text | Record release title. |
| `label` | Text | Record label responsible for the release. |
| `country` | Text | Country or region of release. |
| `format` | Text | Physical release format, such as vinyl or CD. |
| `release_date` | Date/Text | Release date or year. |
| `genre` | Text | Main genre assigned in Discogs. |
| `styles` | Text | Styles or subgenres associated with the release. |
| `have` | Numeric | Number of users who have the release in their collection. |
| `want` | Numeric | Number of users who want to acquire the release. |
| `num_ratings` | Numeric | Total number of ratings received. |
| `average_rating` | Numeric | Average release rating. |
| `lowest_price` | Numeric | Lowest price recorded in the marketplace. |
| `median_price` | Numeric | Median price recorded in the marketplace. |
| `highest_price` | Numeric | Highest price recorded in the marketplace. |

## Final Data Dictionary

The final dataset structure contains 16 columns covering release information, musical classification, collection and wantlist presence, ratings, and prices.

| Column | Data type | Description |
|---|---|---|
| `artist` | Text | Name of the artist, group, or musical project credited on the release. May include collective credits such as `Various` for multi-artist compilations. |
| `title` | Text | Record release title. |
| `label` | Text | Name of the record label associated with the release. |
| `country_clean` | Text | Country of release after cleaning and normalization. Does not necessarily represent the artist's nationality or the label's location. |
| `market_regions` | Text | Region or group of release markets identified during geographic cleaning. Its interpretation depends on the criteria used to separate countries and regions. |
| `format` | Text | Release format recorded in the dataset, for example `Vinyl` or `CD`. |
| `release_year` | Integer | Release year, extracted and normalized from the original date. The intended analysis period is 1990–2000 inclusive. |
| `genre` | Text | Musical genre assigned to the release in the source dataset. |
| `styles_clean` | Text | Style or combination of musical styles associated with the release after cleaning and normalization. A record may include multiple styles. |
| `styles_primary` | Text | First musical style associated with the release after cleaning and normalization. |
| `have` | Integer | Number of Discogs users who had added the release to their collection at extraction time. Does not equal the total number of copies manufactured or sold. |
| `want` | Integer | Number of Discogs users who had added the release to their wantlist at extraction time. Does not represent completed purchases or pending orders. |
| `num_ratings` | Integer | Number of ratings received by the release or edition. Provides context for its average rating. |
| `votes_threshold` | Text | Bands for the number of people who rated the release. |
| `average_rating_clean` | Decimal | Average user rating associated with the release or edition on Discogs. Does not refer to seller reputation or the physical condition grade of a specific copy. Unavailable values were not included as numeric ratings. |
| `lowest_price_clean` | Decimal — monetary amount | Minimum price recorded for the release in the source dataset after cleaning `lowest_price`. Unavailable values were not included as numeric values. |
| `median_price_clean` | Decimal — monetary amount | Median price recorded for the release in the source dataset after cleaning `median_price`. Unavailable values were not included as numeric values. |
| `highest_price_clean` | Decimal — monetary amount | Maximum price recorded for the release in the source dataset after cleaning `highest_price`. Unavailable values were not included as numeric values. |
| `release_display` | Text | Descriptive identification label combining the main details of each release to distinguish it within the analysis. |

## Unit of Analysis

Each row is treated as a record of a release in the dataset, not as a song or an individual sale.

A matching artist and title alone is not used to declare two records duplicates, because they may correspond to different editions or versions of a release.

## Methodological Notes

### Countries and Regions

`country_clean` contains the normalized country of release, while `market_regions` identifies regions or release markets.

### Musical Styles

`styles_clean` may contain several styles for one release, so it should not be interpreted as a single or primary-style classification.

I split and filtered this variable to obtain a list of individual styles. The list serves as a lookup catalog and supports counts by individual style. It does not, by itself, constitute a slicer connected to all dashboard elements.

Calculations that search for complete labels in `styles_clean` include releases containing that style even when they are also assigned other labels. This must not be confused with the `style_primary` filter, which retains only the first style in the source text.

### Missing Values

The original file uses `--` in some ratings and prices. I decided to use `Unknown` for categorical variables and null for quantitative variables.

The specific cleaning documentation explains how these values were handled in each column.

### Ratings and Copy Condition

Average rating is interpreted as users' evaluation of a release or edition, without attributing it exclusively to artistic quality.

The dataset does not include media and sleeve condition for each individual copy or transaction feedback. Therefore, it cannot directly analyze satisfaction with the seller, packaging, shipping, or whether an item matched its description.

### Time Interpretation

`release_year` corresponds to the release's publication year.

Collection, wantlist, rating, and price variables reflect information gathered at extraction time (2023), not necessarily the year of release.

### Price Interpretation

Prices in the original file include the `$` symbol, corresponding to US dollars.

### Data Types

The types in this dictionary are those expected for analysis. Their actual assignment can be checked in `03_discogs_electronic_processed_analytics_dashboard.xlsm`.

## Transformation and Cleaning

## Duplicate Removal or Treatment

As in any data-cleaning process, I had to make strategic decisions about the criteria defining a duplicate. I did not consider every record sharing [artist] and [title] a duplicate: two editions of the same album can represent different releases with different ratings and market prices.

I therefore defined a composite uniqueness key based on six fields: [artist], [title], [label], [country], [format], and [release_year_transformed].

A record was considered a duplicate only when all six fields matched simultaneously. For example, if artist, title, label, country, and format matched but the edition year differed, I treated the record as a different edition or reissue rather than a duplicate.

This decision reflects the logic of the record market: publication year can significantly affect a release's value, since an original edition is not valued in the same way as a later reissue. Retaining records with different [release_year_transformed] values preserves alternative editions of the same album as independent observations.

## Duplicate Review

I subsequently created `Duplicados` as a quality-control worksheet. In it, I generated a dynamic view using `FILTRAR`, extracting only records whose combination of [artist], [title], [label], [country], [format], and [release_year_transformed] appeared more than once.

Detection used `CONTAR.SI.CONJUNTO`, which counts simultaneous matches across multiple columns. Records with counts above 1 were considered duplicates under the defined composite key.

`Duplicados` was not used as the dashboard's main source, but as a review and audit tool before final cleaning.

## Duplicate Removal

After identifying and filtering the records marked `DUPLICADO`, I applied Data > Remove Duplicates to the filtered dataset.

In the settings, I selected only the six columns forming the uniqueness key: [artist], [title], [label], [country], [format], and [release_year_transformed].

Excel retained the first occurrence of each repeated combination and removed subsequent rows with exactly the same key. The operation was permanent, so I kept the original file as a backup to preserve traceability.

The result was a cleaned dataset in which every combination of those six fields appears once. It provides the dashboard's data source and prevents repeated records of the same edition from inflating catalog, rating, or price metrics.

## Control Column

In `Discogs_electronic_cleaning`, I created [duplicate_count] using `SI` and `CONTAR.SI.CONJUNTO`.

The formula compares each row with the complete dataset and counts simultaneous matches on the composite key. Counts above 1 are labeled `DUPLICADO`; otherwise, the row is labeled `ÚNICO`.

```excel
=SI(
  CONTAR.SI.CONJUNTO(
    $A$2:$A$32543; A2;
    $B$2:$B$32543; B2;
    $C$2:$C$32543; C2;
    $D$2:$D$32543; D2;
    $G$2:$G$32543; G2;
    $I$2:$I$32543; I2
  ) > 1;
  "DUPLICADO";
  "ÚNICO"
)
```

[duplicate_count] provided validation and traceability: it allowed me to identify, filter, and review affected records before applying any deletion.

## Excluding Musical Genres

In `Discogs_electronic_cleaning`, because the analysis focuses exclusively on electronic music releases, I filtered [genre] to define the analytical scope. I retained records classified as electronic styles or subgenres and excluded those associated with non-electronic genres.

This ensured that dashboard metrics represented electronic releases only. Excluding records outside that scope was not error correction but an analytical-scope decision aligned with the project's objective.

## Null-Value Handling

For qualitative variables, I decided to replace missing values with `Unknown`; for quantitative variables, I replaced the identified entries with null.

During exploratory analysis, I found missing values in [country] and [styles]. I created [country_clean] and [styles_clean] and labeled missing entries `Unknown` using `SI`, `CONTAR.SI`, and `ESPACIOS`, making them easier to identify in dashboard filters and visualizations.

In [average_rating], [lowest_price], [median_price], and [highest_price], I replaced `--` with null using Find and Replace to represent unavailable data. I retained the rows and did not assign zeros to missing values.

## Checking and Normalizing Cell Formats and Types

The dataset contains incomplete date information. [release_date] is in General format: some entries are short-date strings, others contain only a year and month, and others only a year. To preserve the available information, I standardized the common element—the release year—by creating [release_year] and displaying it using the custom format `aaaa`.

Creating [release_year_transform] from [release_day]:

```excel
=SI(F32504="";"";SI(ESNUMERO(F32504);SI(F32504<10000;F32504;AÑO(F32504));VALOR(IZQUIERDA(ESPACIOS(F32504);4))))
```

Creating [release_year] from [release_year_transform] to normalize the column to a date displayed with the custom format `aaaa`:

```excel
=SI(G32504="";"";FECHA(VALOR(G32504);1;1))
```

I changed [have], [want], and [num_ratings] from General to Number format, removing decimal places.

In [average_rating], [lowest_price], [median_price], and [highest_price], I replaced periods with commas to convert text values to numbers.

To check the types of all final numeric columns, I created [type_control] using:

```excel
=ESNUMERO([@[columna]])
```

[country] contained country names, territories, markets, and geographic regions, so I decided to separate countries from territories, markets, and regions.

I reclassified [country], moving regions, market groups, and territories to a new column, [market_regions]. I reserved the country column for individual countries. This transformation used an auxiliary classification list and `SI`, `CONTAR.SI`, and `ESPACIOS`, without deleting records or splitting them into multiple rows.

[country_clean] and [market_regions] were populated on a mutually exclusive basis: individual countries remained in the former, while regions, groups, and territories moved to the latter. Blanks generated by this classification therefore do not represent information loss. Records without geographic information in the source were labeled `Unknown`.

For [average_rating], I replaced missing-rating markers with null values: missing information must not be confused with numerical zero.

Some numbers used periods and others commas as decimal separators. To standardize the information and allow dashboard calculations, I created `average_rating_clean`, converted the entries to numeric values with commas as decimal separators, and standardized their display to two decimal places.

```excel
=SI(M2="--";"";VALOR(SUSTITUIR(M2;".";",")))
```

The function performed three operations:

- Checked whether the original cell was blank, preserving missing ratings as blank cells.
- Replaced periods with commas through `SUSTITUIR`, standardizing the decimal separator.
- Converted the resulting text to a number through `VALOR`.

[average_rating_clean_2] contains the average ratings in numeric format with a standardized decimal separator. It supports average-rating indicators, identification of highly rated releases, and comparisons by style, artist, year, or other dashboard dimensions.

I kept [average_rating] and [average_rating_clean_1] as backups of the transformation process. Normalization took place in a separate column to avoid modifying the original data directly.

Cells without ratings remained null.

[lowest_price], [median_price], and [highest_price] were stored as text, with a currency symbol preceding the decimal number and dash markers for missing values. I removed `$`, converted all decimal separators to commas, and then reapplied currency formatting with `$`.

`--` values must remain null, because they do not represent prices and missing information must not be confused with zero.

`SI` returns different results depending on a condition; here, it treats dash markers and blank cells as missing prices.

```excel
=SI(O(T2="--";T2="");"";VALOR(SUSTITUIR(SUSTITUIR(T2;"$";"");".";",")))
```

This formula performs the following:

- If the value is `--` or blank, returns a blank cell.
- If there is a price, removes `$`.
- Replaces the decimal period with a comma.
- Converts the result to a number through `VALOR`.

Musical style treatment and creation of the lookup catalog:

`styles_clean` contained one or more comma-separated styles per release. To support queries by individual style, I built a unique catalog using Excel formulas in auxiliary worksheets.

This preserved the original column and maintained one row per release in the main table, avoiding multiplication of records for every associated style.

1. Extracting combinations

I created `Styles_catalog` with `styles` in A1. In A2, I entered a structured reference to the source column:

```excel
=discogs_electronic[styles_clean]
```

This transfers the style combinations to the auxiliary worksheet while keeping their link to the main table.

2. Splitting and normalizing styles

In B2, I entered the following formula and extended it to the final data row:

```excel
=SI(A2="";"";ESPACIOS(DIVIDIRTEXTO(A2;",")))
```

The formula leaves rows without information blank, splits the labels using commas as delimiters, and removes excess spaces using `ESPACIOS`.

Each release's styles are distributed horizontally across separate columns:

```text
[House,Tech House,Trance,Deep House]: [House] [Tech House] [Trance] [Deep House]
```

### Building the Unique Style Catalog

In `Styles_list`, I generated a unique style catalog from `Styles_catalog!B2:AE29972`, where the styles of each release had already been separated into columns.

I used:

```excel
=LET(styles;ENCOL(Styles_catalog!B2:AE29972;3);ORDENAR(UNICOS(FILTRAR(styles;styles<>""))))
```

I created `Styles_list` and built a unique sorted list of the styles already distributed across the columns of [Styles_catalog]. This does not count releases or split comma-separated text itself: it consolidates previously separated styles.

## New Column: [style_primary]

### Objective

Create a primary-style category to filter the dashboard by a single electronic style. The original [styles_clean] can contain several comma-separated styles, making it unsuitable as a direct slicer.

### Transformation Rule

[style_primary] retains only the first style in [styles_clean], before the first comma.

Formula applied to the first data row:

```excel
=SI.ERROR(IZQUIERDA(I2;ENCONTRAR(",";I2)-1);I2)
```

### Release Counts by Style

In `Analytics`, I built a summary table from the individual-style catalog.

A formula counts the records in [styles_clean], in `Discogs_electronic_processed_analytics_dashboard`, containing each style. It searches complete labels to avoid partial matches between styles such as House, Deep House, and Tech House.

The same release can be counted under several styles. The sum of style counts may therefore exceed the total number of releases analyzed.

The procedure consisted of:

1. Consolidating styles spread across several columns into one list with `ENCOL`, ignoring blank cells and errors.
2. Assigning the temporary name `styles` with `LET` to facilitate reuse in the formula.
3. Excluding empty strings with `FILTRAR`.
4. Keeping a single occurrence of each style with `UNICOS`.
5. Sorting alphabetically with `ORDENAR`.

The result is a non-repeating catalog of individual styles, supporting lookups and counts in the analysis and dashboard.

This does not modify the main table or multiply its records. Release–style associations remain in [styles_clean].

The catalog alone does not create an automatic relationship with releases or dashboard slicers; those associations are implemented through the corresponding lookup and counting formulas.

I identified 307 distinct musical styles and 63,983 release–style associations.

One release can belong to several styles, so the sum of style counts exceeds the number of releases. The resulting average is approximately 2.14 styles per release.

### Record Identifiers

In `Discogs_electronic_cleaning`, in `02_discogs_electronic_data_cleaning.xlsx`, I created a new label, [release_display], because there was no record identifier.

I used:

```excel
=A2&" — "&B2&" | "&C2&" | "&SI(E2<>"";E2;F2)&" | "&TEXTO(J2;"aaaa")&" | “&K2&" | fila "&FILA()
```

The label shows artist, title, label, country or region, format, and year. The row suffix prevents two records with the same attributes from merging in the PivotTable. It is a working identifier, not a permanent Discogs identifier.

## Creating the New Column: `votes_threshold`

In `Discogs_electronic_processed`, I created `votes_threshold` from `num_ratings` to categorize rating counts into bands and filter the top ten highest-rated releases.

The bands are mutually exclusive, not cumulative thresholds: selecting `100–199` is not equivalent to selecting every release with at least 100 ratings; `500+` does correspond to 500 or more ratings. The purpose is to distinguish ratings supported by different levels of community participation.

### Transformation Rule

`votes_threshold` groups `num_ratings` into bands of 100 ratings:

| Category | Rule |
|---|---|
| `0–99` | Fewer than 100 ratings |
| `100–199` | 100 to 199 ratings |
| `200–299` | 200 to 299 ratings |
| `300–399` | 300 to 399 ratings |
| `400–499` | 400 to 499 ratings |
| `500+` | 500 ratings or more |

I applied the formula to the first data row of `votes_threshold`, referring to M2, the first data cell of `num_ratings`:

```excel
=SI(M2>=500;"500+";SI(M2>=400;"400–499";SI(M2>=300;"300–399";SI(M2>=200;"200–299";SI(M2>=100;"100–199";"0–99")))))
```

## Preparing Auxiliary Worksheets for Relationship Analysis

### 1. Objective

To answer “What relationship exists between collection ownership, demand, ratings, and prices?”, I created five auxiliary worksheets from `Discogs_electronic_processed`:

- `Want_price`
- `Have_price`
- `Rating_want`
- `Rating_have`
- `Rating_price`

These worksheets prepare valid paired observations, calculate Pearson correlations, and support scatterplots without modifying the processed dataset.

Separating the variable pairs improves analytical traceability: each sheet contains only the variables and records required to study a particular relationship.

### 2. Data Source and Unit of Analysis

I used the following columns:

| Column | Variable | Use |
|---|---|---|
| J | `have` | Release presence in collections |
| K | `want` | Release presence on wantlists |
| L | `num_ratings` | Number of recorded ratings |
| M | `average_rating_clean` | Cleaned average rating |
| O | `median_price_clean` | Cleaned median price |

The unit of analysis is each release record. Different editions of a work were not grouped by artist or title.

Ownership, demand, rating, and price indicators refer to the time of data collection. The 1990–2000 period refers to release years, not the timing of user activity.

### 3. Inclusion Criteria

I applied a valid-record selection specific to each relationship.

| Worksheet | X variable | Y variable | Inclusion criterion |
|---|---|---|---|
| `Want_price` | `want` | `median_price_clean` | Both numeric |
| `Have_price` | `have` | `median_price_clean` | Both numeric |
| `Rating_want` | `average_rating_clean` | `want` | Both numeric and `num_ratings > 0` |
| `Rating_have` | `average_rating_clean` | `have` | Both numeric and `num_ratings > 0` |
| `Rating_price` | `average_rating_clean` | `median_price_clean` | Both numeric and `num_ratings > 0` |

I did not replace missing values with zero. Records failing the criteria were excluded only from the corresponding relationship and retained in the processed worksheet.

The numeric criterion preserves existing zeros, so this selection does not require strictly positive values.

For rating relationships, I required at least one rating to avoid treating releases without ratings as having a valid score.

### 4. Implementation Logic

Each auxiliary worksheet has two columns:

- Column A: X-axis variable.
- Column B: Y-axis variable.

Extraction uses formulas with:

- `LET` to define ranges and selection conditions.
- `ESNUMERO` to verify numeric variables.
- `FILTRAR` to return qualifying records.

I applied exactly the same condition to both columns. Each output row therefore retains values belonging to the same release.

I did not filter or sort the variables independently, as that would break the pairing required for analysis.

#### Example: `Want_price`

In A2, I extracted valid demand values:

```excel
=LET(
demanda;Discogs_electronic_processed!K2:K29927;
precio;Discogs_electronic_processed!O2:O29927;
validos;ESNUMERO(demanda)*ESNUMERO(precio);
FILTRAR(demanda;validos)
)
```

In B2, I used the same condition to extract prices:

```excel
=LET(
demanda;Discogs_electronic_processed!K2:K29927;
precio;Discogs_electronic_processed!O2:O29927;
validos;ESNUMERO(demanda)*ESNUMERO(precio);
FILTRAR(precio;validos)
)
```

For `Have_price`, I substituted the `have` range for `want`, retaining the same procedure.

#### Example: `Rating_price`

For rating relationships, I added `num_ratings > 0`. In A2:

```excel
=LET(
valoracion;Discogs_electronic_processed!M2:M29927;
precio;Discogs_electronic_processed!O2:O29927;
votos;Discogs_electronic_processed!L2:L29927;
validos;ESNUMERO(valoracion)*ESNUMERO(precio)*(votos>0);
FILTRAR(valoracion;validos)
)
```

B2 retained the same definitions and conditions, changing only the final expression to:

```excel
FILTRAR(precio;validos)
```

I used the same logic in `Rating_want` and `Rating_have`, replacing price with demand or ownership respectively.

### 5. Dynamic Arrays and Observation Counts

The formulas generate dynamic arrays from A2 and B2. `A2#` and `B2#` refer to the full results returned by each formula.

I counted included observations with:

```excel
=FILAS(A2#)
```

As a pairing check, both columns in a worksheet must contain the same number of rows.

The source ranges are fixed and extend through row 29927.

### 6. Correlation Calculations

I calculated the coefficients with `COEF.DE.CORREL` over the filtered columns of each worksheet:

```excel
=COEF.DE.CORREL(Want_price!A2#;Want_price!B2#)
```

```excel
=COEF.DE.CORREL(Have_price!A2#;Have_price!B2#)
```

```excel
=COEF.DE.CORREL(Rating_want!A2#;Rating_want!B2#)
```

```excel
=COEF.DE.CORREL(Rating_have!A2#;Rating_have!B2#)
```

```excel
=COEF.DE.CORREL(Rating_price!A2#;Rating_price!B2#)
```

I displayed results to three decimal places and recorded the valid-pair count for each relationship.

### 7. Analytical Samples and Results

| Worksheet | Valid pairs | Records excluded from the relationship | Pearson |
|---|---:|---:|---:|
| `Want_price` | 29,414 | 512 | 0.600 |
| `Have_price` | 29,414 | 512 | 0.130 |
| `Rating_want` | 29,192 | 734 | 0.276 |
| `Rating_have` | 29,132 | 794 | 0.174 |
| `Rating_price` | 28,903 | 1,023 | 0.271 |

Exclusions are calculated against the 29,926 original records.

These counts must not be added across worksheets: a release may be excluded from several relationships.

Differences between analytical samples are consistent with criteria applied to different variables. Without reviewing individual records, exclusions cannot all be attributed solely to null values: nonnumeric values and the rating-count condition may also contribute.

Likewise, identical observation counts do not prove that two worksheets contain exactly the same records.

### 8. Relationship Visualizations

I built a scatterplot for each auxiliary worksheet, using the same paired observations as the correlation calculation.

| Worksheet | X axis | Y axis | Chart title |
|---|---|---|---|
| `Want_price` | Want | Median Price | Demand vs Median Price |
| `Have_price` | Have | Median Price | Collection vs Median Price |
| `Rating_want` | Average Rating | Want | Average Rating vs Demand |
| `Rating_have` | Average Rating | Have | Average Rating vs Collection |
| `Rating_price` | Average Rating | Median Price | Average Rating vs Median Price |

Each point represents one release record.

I retained outliers at this exploratory stage and did not apply logarithmic transformations. The charts complement the coefficients, allowing examination of dispersion and observations far from the main concentration.

### 9. Analytical Summary

Demand and median price had the highest correlation among these five worksheets, at 0.600. This supports a positive linear association between interest in obtaining a release and its median price.

The relationship between collection ownership and price was much smaller, at 0.130. The most widely owned releases are therefore not necessarily the most expensive.

Average rating had weak positive associations with:

- Demand: 0.276.
- Collection ownership: 0.174.
- Median price: 0.271.

Together, these results show that ownership, demand, rating, and price describe related but distinct dimensions of the behavior observed in the sample.

### 10. Limitations

- Pearson correlation summarizes linear associations and does not establish causation.
- A weak correlation does not rule out nonlinear relationships.
- Extreme values may influence the coefficients.
- Each relationship uses its own valid sample; I did not impose a common sample across comparisons.
- Differences between coefficients are interpreted descriptively; no formal comparison test was performed.
- In rating analyses, every release receives the same weight regardless of rating count.
- Requiring `num_ratings > 0` does not ensure equal support for all average ratings.
- Numeric selection alone does not validate currency, provenance, or price plausibility.
- Results are limited to the analyzed dataset and do not necessarily represent the entire electronic music market.

## `Style_price`: Median Price Analysis by Style

I added `Style_price` to answer:

> Which styles have the highest median prices?

For each style label, the sheet calculates:

- The number of releases with numeric prices.
- The median of their individual median release prices.
- Their position in a style ranking meeting a minimum observation count.

This complements the ranking by release volume: it measures prices, not production.

## Data Source

Calculations use `Discogs_electronic_processed`, containing 29,926 records excluding the header.

| Source column | Variable | Range used |
|---|---|---|
| I | `styles_clean` | `I2:I29927` |
| O | `median_price_clean` | `O2:O29927` |

The individual-style list comes from the catalog prepared in `Styles_list`.

Source ranges are fixed. If records are added beyond row 29927, the references must be updated.

### Worksheet Structure

I organized the sheet into two blocks:

| Column | Header | Content |
|---|---|---|
| A | `style` | Individual-style catalog |
| B | `releases_with_price` | Releases of the style with numeric prices |
| C | `median_release_price` | Median of those releases' median prices |
| E | `Style` | Styles selected and sorted for the ranking |
| F | `Releases with price` | Corresponding count for each ranked style |
| G | `Median release price` | Corresponding median for each ranked style |

Column D provides visual separation.

A:C retains the full summary. E:G contains up to 100 styles, sorted by descending median price.

I kept the blocks as normal ranges rather than Excel tables to allow formulas with spilled results.

### Identifying Styles Within Releases

A release can have several labels in `styles_clean`.

I searched for comma-delimited matches instead of partial text matches:

```excel
ESNUMERO(HALLAR(","&A2&",";","&estilos&","))
```

For example, searching for `,House,` does not match `,Deep House,`.

This assumes comma-separated labels without extra spaces beside delimiters. Its operation depends on preserving the normalization of `styles_clean`.

A release may appear in several groups. Style counts are therefore not mutually exclusive and must not be summed to obtain total releases.

### Counting Releases with Numeric Prices

In B2:

```excel
=LET(
estilos;Discogs_electronic_processed!I2:I29927;
precios;Discogs_electronic_processed!O2:O29927;
coincide;ESNUMERO(HALLAR(","&A2&",";","&estilos&","));
SUMAPRODUCTO(--coincide;--ESNUMERO(precios))
)
```

The formula counts records meeting both conditions:

1. The release contains the style specified in A2.
2. `median_price_clean` is numeric.

I copied the formula to the last style in the catalog.

Missing prices and prices stored as text were excluded, not replaced with zero.

`ESNUMERO` preserves existing numeric zeros; it does not require strictly positive prices.

### 6. Calculating Median Price by Style

In C2:

```excel
=SI(B2=0;"";LET(
estilos;Discogs_electronic_processed!I2:I29927;
precios;Discogs_electronic_processed!O2:O29927;
coincide;ESNUMERO(HALLAR(","&A2&",";","&estilos&","));
MEDIANA(FILTRAR(precios;coincide*ESNUMERO(precios)))
))
```

The formula:

1. Checks whether the style has records with numeric prices.
2. Filters prices of releases associated with the style.
3. Calculates the median of the selected values.
4. Returns a visually blank cell if no valid observations exist.

I copied it through the last style.

The resulting indicator is the median of `median_price_clean` across releases. It is neither an arithmetic mean nor the median of all individual Discogs transactions.

Every release contributes one value, without weighting by sales, users, or ratings.

### Ranking Inclusion Criteria

A:C retains all styles, including those without numeric prices or with few observations.

For E:G, I required:

- A nonempty style label.
- At least 30 releases with numeric prices.
- A numeric median.

I adopted the 30-record minimum as a practical criterion to prevent groups with very few observations from dominating the main ranking.

The threshold is not a statistical guarantee of representativeness. Styles failing it remain in the dataset and full summary; they are excluded only from the selected ranking.

### Generating the Dynamic Ranking

The ranking initially included ten styles and was later expanded to a maximum of 100.

In E2:

```excel
=LET(
estilos;$A$2:$A$1000;
recuentos;$B$2:$B$1000;
precios;$C$2:$C$1000;
validos;(estilos<>"")*(recuentos>=30)*ESNUMERO(precios);
lista;FILTRAR(estilos;validos);
medianas;FILTRAR(precios;validos);
ordenados;ORDENARPOR(lista;medianas;-1;lista;1);
INDICE(ordenados;SECUENCIA(MIN(100;FILAS(ordenados))))
)
```

The formula:

1. Filters styles meeting the criteria.
2. Sorts them by descending median price.
3. Uses alphabetical style order when median values are exactly equal.
4. Returns up to 100 styles.

The expression:

```excel
MIN(100;FILAS(ordenados))
```

limits output to the available styles when fewer than 100 qualify.

The formula assumes at least one eligible style, a condition met in the analyzed dataset.

Selection uses underlying cell values, not rounded displayed values. Two medians displayed identically to two decimals may sort differently if their internal precision differs.

### Retrieving Associated Values

In F2, I retrieved counts of releases with prices:

```excel
=BUSCARX(E2#;$A$2:$A$1000;$B$2:$B$1000;"";0)
```

In G2, I retrieved median prices:

```excel
=BUSCARX(E2#;$A$2:$A$1000;$C$2:$C$1000;"";0)
```

These formulas use exact matches and reference the spilled list in E2.

Styles, counts, and medians therefore remain aligned in ranking order.

Formulas are entered only in E2, F2, and G2. Cells below must remain free to allow expansion.

Lookup ranges extend through row 1000. If the catalog exceeds that limit, all three formulas must be updated.

### Consistency Checks

I established the following checks:

- Every ranked style must have at least 30 records with prices.
- Medians must be sorted from highest to lowest.
- F:G must match the same style's values in A:C.
- All three ranking columns must have equal row counts.
- A must contain only one entry per style.
- Results must not contain spill or reference errors.

The number of included styles can be checked with:

```excel
=FILAS(E2#)
```

Lengths of the associated columns can also be checked:

```excel
=FILAS(F2#)
```

```excel
=FILAS(G2#)
```

All three results must match.

### Style Price Chart

I created a horizontal bar chart using the first ten ranked styles.

| Element | Configuration |
|---|---|
| Categories | `E2:E11` |
| Values | `G2:G11` |
| Type | 2D clustered bars |
| Title | `Top 10 Styles by Median Release Price` |
| Visual order | Highest median price at the top |
| Labels | Price to two decimal places |

F remains supporting information and is not plotted as a second bar series.

The auxiliary ranking contains up to 100 styles, while the chart shows only the first ten.

I added this methodological note:

> Only styles with at least 30 releases with numeric prices are included. Each value is the median of the median prices of releases associated with the style. One release may belong to several styles.

I retained the existing monetary format without assigning a specific currency until the source field's unit is confirmed.

### Scope and Limitations

- The analysis describes price differences between styles within the dataset.
- It does not measure historical price changes or establish appreciation in value.
- 1990–2000 refers to release years, not necessarily price-observation dates.
- Style labels overlap and group sizes differ.
- A difference between medians does not show that style causes price differences.
- Numeric selection alone does not verify currency, plausibility, or comparability.
- I applied no additional outlier exclusion in this procedure.
- Formulas recalculate within defined ranges; they do not automatically include records outside them.

## Annual Style Evolution: Cross-Tabulation in `Analytics`

I added a cross-tabulation to `Analytics` to analyze how the presence of five selected styles changed between 1990 and 2000:

- House.
- Deep House.
- Garage House.
- Techno.
- Progressive House.

The selection corresponds to the styles in one initial hypothesis.

The objective is to compare their relative presence within each year's releases, distinguishing changes in composition from changes in total release volume.

### Location and Organization

I initially prepared the logic in `Styles_evolution`.

I later moved the table and formulas to `Analytics` and deleted the separate sheet, centralizing analysis and reducing the number of worksheets.

The percentage-analysis supporting table uses formulas, not an Excel PivotTable. This must be distinguished from the final `Selected styles by year` PivotChart, whose response to YEAR was checked subsequently. Percentages in this section belong to the auxiliary analysis and do not by themselves establish the metric or exact source of the final chart's series.

Its logical structure is:

| Field | Content |
|---|---|
| `year` | Release year, 1990–2000 |
| `total_releases` | Total releases in the year |
| `House` | Annual proportion containing this label |
| `Deep House` | Annual proportion containing this label |
| `Garage House` | Annual proportion containing this label |
| `Techno` | Annual proportion containing this label |
| `Progressive House` | Annual proportion containing this label |

Coordinates in these examples are illustrative and correspond to the initial layout:

- A1:G1: headers.
- A2:A12: years.
- B2:B12: annual totals.
- C2:G12: style proportions.

In `Analytics`, year, total, and header references correspond to the actual block location.

### Data Source

I used `Discogs_electronic_processed`, with 29,926 records and headers in row 1.

| Column | Variable | Range used |
|---|---|---|
| G | `release_year` | `G2:G29927` |
| I | `styles_clean` | `I2:I29927` |

No price, ownership, demand, or rating filters were applied. The analysis uses all releases in each year.

Source ranges are fixed. If the dataset grows beyond row 29927, formulas must be updated.

### Handling Release Years

During implementation, I checked that `release_year` contains Excel dates although the cells display only the year through formatting.

I therefore did not compare column G directly with numbers such as `1990`.

Each year's records were identified using two limits:

- On or after January 1 of the analyzed year.
- Before January 1 of the following year.

The analysis table's `year` field contains integer years, not full dates.

I did not modify the source column.

### Calculating Annual Release Totals

With the year in A2, the reference formula for `total_releases` is:

```excel
=CONTAR.SI.CONJUNTO(
Discogs_electronic_processed!$G$2:$G$29927;">="&FECHA($A2;1;1);
Discogs_electronic_processed!$G$2:$G$29927;"<"&FECHA($A2+1;1;1)
)
```

I repeated this calculation for the eleven years from 1990 to 2000.

An exclusive upper bound includes all dates in the year without depending on records being stored specifically as January 1.

As an initial check, 1990 returned 1,757 releases, matching the annual PivotTable already used in the project.

### Identifying Style Labels

`styles_clean` can contain several comma-separated labels.

I used a delimited search:

```excel
ESNUMERO(HALLAR(","&C$1&",";","&estilos&","))
```

Adding commas at the beginning and end supports complete-label searches.

For example:

- `House` is identified as a separate label.
- Searching for House does not automatically count Deep House or Progressive House.
- A release containing both House and Deep House participates in both groups.

This assumes normalized comma separation without extra spaces beside delimiters.

Table headers must match the catalog labels.

### Calculating Annual Style Presence

The indicator is:

```text
Annual style presence =
releases in the year containing the style /
total releases in the year
```

The reference formula, initially in C2, is:

```excel
=LET(
fechas;Discogs_electronic_processed!$G$2:$G$29927;
estilos;Discogs_electronic_processed!$I$2:$I$29927;
coincide;ESNUMERO(HALLAR(","&C$1&",";","&estilos&","));
desde;FECHA($A2;1;1);
hasta;FECHA($A2+1;1;1);
SI($B2=0;"";SUMAPRODUCTO(
--(fechas>=desde);
--(fechas<hasta);
--coincide
)/$B2)
)
```

The formula:

1. Defines date and style ranges.
2. Identifies the label in the header.
3. Selects records from the row's year.
4. Counts releases meeting both conditions.
5. Divides the count by the annual total.
6. Returns a visually blank cell if the denominator is zero.

I copied the calculation rightward across five styles and downward across eleven years.

Results are stored as proportions and displayed as percentages. They are not multiplied by 100 again.

### Denominator and Overlapping Categories

The denominator is the year's total release count, not the sum of occurrences of the five styles.

Therefore:

- One release can contribute to several style numerators.
- A row's percentages need not add to 100%.
- This is not an exclusive distribution among five styles.
- Records without these style labels remain in the annual denominator.

The indicator measures each label's presence among all releases in the year.

### Percentage Visualization and Distinction from the Dashboard

The following configuration documents the percentage-analysis visualization. It must not automatically be attributed to the final PivotChart, which was retained to preserve YEAR interactivity.

I defined a non-stacked line chart with one series per style.

| Element | Configuration |
|---|---|
| Title | `Selected Electronic Styles by Year (1990–2000)` |
| Horizontal axis | Years 1990–2000 |
| Vertical axis | Percentage of annual releases |
| Series | House, Deep House, Garage House, Techno, Progressive House |
| Type | Non-stacked lines with markers |
| Supporting table | Percentages to two decimal places |

`total_releases` is excluded as a series because it contains counts in a different unit.

I did not use a 100% stacked chart because style categories overlap.

Methodological note:

> Percentage of each year's releases containing each selected style. Labels may overlap; percentages do not necessarily add to 100%.

### Scope and Limitations

- The analysis describes dataset releases, not sales, revenue, or audience.
- A declining percentage does not necessarily imply fewer releases in absolute terms.
- The five styles reflect the initial hypothesis, not the dataset's full stylistic diversity.
- Results alone cannot establish whether market diversity increased or decreased.
- Labels are analyzed independently, without automatically merging subgenres into a main category.
- Observed changes are descriptive and do not identify causes.
- Centralizing the analysis in `Analytics` changes workbook organization, not calculation criteria.

## Control Functions in `Analytics`

`Analytics` contains several data-checking and information functions.

Unique Artists checks unique values across the artist column:

```excel
=FILAS(UNICOS(discogs_electronic_processed[artist]))
```

Missing Data Check checks blank values across columns:

```excel
=CONTAR.BLANCO(discogs_electronic_processed[artist])
```

## Answers to the Research Questions

1. How did the number of releases evolve between 1990 and 2000?

I observed increases, decreases, and fluctuations between 1990 and 1994, and identified 1996 as the peak year of the entire period.

The conclusion concerns releases in the sample, not all electronic music production worldwide. An increase between the first and last year does not necessarily imply continuous growth: the chart distinguishes these situations.

2. Which styles and subgenres accounted for the most releases?

House had the largest presence, with 11,838 associated releases, followed by Techno with 9,536. Both were clearly ahead of the rest: Progressive House ranked third with 4,414, followed by Tech House with 3,754 and Electro with 3,678.

Ambient and Trance also had substantial representation, with 2,494 and 2,133 releases respectively.

The initial hypothesis is partially supported. House, Techno, Progressive House, and Deep House appear among the ten styles with the most releases, while Garage House ranks 13th.

Tech House and Electro are also more frequent than Deep House and Garage House.

These results describe style presence in the analyzed sample, not sales shares or shares of all electronic music production during the period.

A release may be associated with several styles. Counts are therefore not mutually exclusive and must not be added as if they represented different releases.

3. Which record labels were the most prolific?

Virgin led the sample with 315 releases, followed by Epic with 263 and Columbia with 245. Among labels in the initial hypothesis, FFRR and Strictly Rhythm had a substantial presence, with 185 and 179 releases respectively. Deconstruction had 115 and ranked 15th in the original classification.

Results partially support the hypothesis: some expected labels appear among the most frequent, but none leads the ranking. It describes records associated with each label name in the sample, not sales, influence, or total production during the period.

I excluded `Not On Label` from the ranking. In Discogs, this does not represent one label but a category called a meta-label for releases without an identifiable record label.

Those records remain in the dataset.

4. Which countries accounted for the most release activity?

The country analysis includes 27,645 records with identified countries. The ranking excludes 1,012 records classified as `Unknown` and 1,270 without an individual country in [country_clean], whose geographic information is in [market_zones]. All records remain in the dataset.

The United Kingdom [UK] led with 9,775 releases, followed by the United States with 6,755, Germany with 3,637, and Italy with 2,606. The Netherlands ranked fifth with 1,190.

Results support the expected prominence of the United Kingdom, United States, Germany, Italy, Netherlands, and France, all among the sample's top seven countries. Belgium also had substantial participation, ranking ahead of France.

These results describe the geographic distribution of releases in the dataset, not necessarily artists' countries of origin or all electronic music production. The ranking excludes `Unknown` and records classified only by market region (null).

5. Which physical format dominated, and how did it evolve?

Vinyl dominated the sample with 26,940 records, approximately 90.02%, followed by CD with 2,957, or 9.88%. Other categories had a residual presence.

CD increased from 96 releases in 1990 to 420 in 2000. Its maximum was 453 in 1999. It also fluctuated: for example, it fell from 293 in 1995 to 290 in 1996.

CD gained share, rising from approximately 5.5% of annual releases in 1990 to 13.2% in 2000, with a peak near 15.5% in 1999. Nevertheless, it did not replace vinyl as the sample's main format. These percentages use each year's total, including all formats.

Results support vinyl dominance in the dataset, but do not establish by themselves that all those releases were club- or DJ-oriented.

Vinyl rose from 1,653 releases in 1990 to a peak of 3,221 in 1996, then fell to 2,473 in 1999 and rebounded to 2,750 in 2000. Growth was therefore not continuous.

6. Which releases attracted the greatest collection and demand interest?

The most widely owned release was *#1* by Mr. Oizo, with 10,643 in [have], followed by *Knights Of The Jaguar EP* by The Aztec Mystic with 7,689, and *American Pie* by Madonna with 7,290. Thomas Bangalter (one half of Daft Punk) stood out by placing three releases among the ten most widely owned.

For demand, *Knights Of The Jaguar EP* led with 7,511 in [want], followed by *6 Millions Pintades EP* by Pépé Bradock with 6,838 and *Trax On Da Rocks Vol. 2* by Thomas Bangalter with 5,390. All ten most-wanted releases were vinyl editions.

Four records appeared in both top tens, showing partial overlap between ownership and demand. However, differences in position show that the most widely owned releases are not necessarily the most wanted. Rankings describe specific editions in the sample, not totals across all editions of a work.

The indicators reflect collection and wantlist status at data collection time. The 1990–2000 period refers to release years, not when users added them.

7. What relationship exists between [have], [want], [num_ratings], [average_rating_clean], and [lowest_price_clean], [median_price_clean], [highest_price_clean]?

[have] vs [want]

The Pearson correlation was 0.593, indicating a moderate positive linear association. Releases present in more collections also tended to attract more users interested in obtaining them.

However, the chart shows considerable dispersion and many records concentrated at low values of both variables. It also contains releases with exceptionally high ownership or demand. Overall, the indicators are related but not equivalent, and the association does not establish causation.

[want] vs [median_price_clean]

I analyzed 29,414 releases with numeric values in both variables. Pearson correlation was 0.600, consistent with a moderate positive linear association.

The chart nevertheless shows considerable dispersion: releases with similar demand can have very different prices. The highest median prices also do not belong to the most-wanted records. The result supports a positive association between demand and price in the sample, not a proportional or causal relationship.

[have] vs [median_price_clean]

I analyzed 29,414 releases with numeric values in both variables. Pearson correlation was 0.130, indicating a very weak positive linear association. The chart shows that the most widely owned releases are not necessarily the most expensive.

By contrast, demand (`want`) and median price had a correlation of 0.600. In these analyses, demand therefore has a stronger linear association with price than collection ownership, without implying causation.

[average_rating_clean] vs [want]

I analyzed 29,192 releases with numeric values in both variables and at least one recorded rating, [num_ratings] > 0.

The Pearson correlation was 0.276, consistent with a weak positive linear association. Higher-rated releases tend to have greater demand, although average rating alone cannot precisely predict interest in obtaining a release.

The 734 records failing inclusion criteria were excluded only from this relationship and retained in the processed dataset.

The analysis assigns equal weight to every release, regardless of rating count. A score based on a few ratings therefore contributes just as much as one supported by hundreds.

This association does not show that higher ratings cause greater demand.

[average_rating_clean] vs [have]

I analyzed 29,132 releases with numeric values in both variables and at least one recorded rating, [num_ratings] > 0.

Pearson correlation was 0.174, a very weak positive linear association. Higher-rated releases tend slightly toward greater collection presence, but a high rating does not necessarily imply many owners.

The ownership association is smaller than the 0.276 for [average_rating_clean] vs [want]. This comparison is descriptive because the analyses may use different sets of valid records.

In conclusion, average rating has little linear association with `have` in the sample. Results are not causal and must be interpreted considering that each release receives equal weight regardless of the ratings supporting its average.

[average_rating_clean] vs [median_price_clean]

I analyzed 28,903 releases with numeric values in both variables and at least one recorded rating, [num_ratings] > 0.

Pearson correlation was 0.271, indicating a weak positive linear association. Higher-rated releases tend slightly toward higher median prices, but a high score does not necessarily imply a high price.

The result does not establish causation. Each release receives equal weight regardless of rating count. The 1,023 records failing inclusion criteria were excluded only from this relationship and retained in the processed dataset.

## Overall Assessment

The hypothesis that more-wanted releases may have higher median prices is supported within the sample by the 0.600 correlation.

The hypothesis linking ratings with collection interest receives limited support: associations are positive but weak. Nor can we conclude that rating and price are unrelated: their positive correlation was 0.271, similar in magnitude to the relationship between rating and demand.

These results are descriptive, use valid samples that may differ, and cannot establish which variable causes another.

8. Which styles reached the highest market prices?

Freetekno and Minimal Techno had the highest medians in the ranking, both displayed as $16.30, supported by 38 and 72 releases with prices respectively.

They were followed by Bleep at $10.87 with 202 records, Dub Techno at $10.76 with 59, and IDM at $8.70 with 318.

Among styles with larger samples, Minimal, Acid, Experimental, and Ambient also stood out. In contrast, House and Techno, which led by release volume, had medians of $3.24 and $5.43 respectively.

The highest-volume styles were not necessarily those with the highest median prices. Freetekno and Minimal Techno led among styles with at least 30 records with prices, followed by Bleep and Dub Techno.

These are descriptive differences between style labels, not evidence that style determines a release's value. Nor do they demonstrate historical appreciation, since the analysis compares observed prices for releases published in 1990–2000, not price changes over time.

Group sizes differ and style labels overlap: a release may contribute to several styles.

9. Which artists and labels were associated with the highest-rated releases?

In [Top_rated_releases], I selected the ten releases with the highest average ratings among those with at least 500 ratings, sorted by descending score and, for ties, by rating count.

The following results refer to that auxiliary analysis. The dashboard chart uses a different implementation: a PivotTable in `Analytics`, an output block, and the `Votes threshold` slicer. The auxiliary worksheet's fixed minimum and tie-breaker must therefore not automatically be attributed to the interactive chart.

Choice led with *Acid Eiffel / How Do You Plead?*, released by Fragile Records, with a rating of $4.82 and 771 ratings. Galaxy 2 Galaxy followed with $4.78 and 911 ratings, then Pépé Bradock with *Burning*, at $4.77 and 1,039 ratings. Aril Brikha, Sasha, Drexciya, The Aztec Mystic, DJ Rolando, Ron Trent, and Maurizio also appeared.

By label, Underground Resistance accounted for four of the ten records and Fragile Records for two. Kif Recordings, Deconstruction, Djax-Up-Beats, and Maurizio each appeared once. Underground Resistance and Fragile Records therefore stood out within this selection of highly rated releases.

## Comparison with the Initial Hypotheses

This question provides an exploratory result but does not directly validate or reject an initial hypothesis.

The hypothesis about particularly active labels concerns publication counts, while this ranking concerns ratings of individual releases. Deconstruction's presence, although it was an initially proposed label, does not establish that it was among the most productive.

This finding complements the label-volume analysis but does not establish that these labels were the most productive or highest-rated across their whole catalogs.

The hypothesis about [num_ratings], [want], and price must be assessed using the relationships in question 7, not this ranking.

The 500-rating minimum limits selection to releases with greater user participation, but does not make the ranking representative of all releases.

10. How did the composition of the electronic music market change throughout the decade?

Between 1990 and 2000, the analyzed releases changed in format, style, and geographic composition. Vinyl remained dominant, while CD gained share.

Among the selected styles, House lost relative presence, Techno was particularly prominent early in the period, and Progressive House expanded. Geographically, the United Kingdom strengthened its position, Germany and France increased their shares, and the United States ended with a smaller share than in 1990.

These results describe changes in dataset composition, not sales shares or causal relationships. A percentage decline does not necessarily mean fewer releases, and the evolution of five styles cannot characterize all electronic music diversity. Geographic interpretation must also consider records without identified countries or classified only by market region.

The following verdicts are descriptive: they indicate how far dataset findings support each proposition. They are not formal statistical tests and cannot automatically be generalized to the entire electronic music market.

## 1. Release Counts Grew During the First Half of the 1990s

Verdict: supported as a general trend, but not as continuous growth.

Releases increased from 1,757 in 1990 to 2,394 in 1994 and reached 3,072 in 1995. However, 1994 saw a small decrease from 2,418 in 1993. The period's maximum was 3,516 in 1996.

The dataset therefore supports expansion from the early to mid-1990s, with year-to-year fluctuations.

## 2. Vinyl Was the Dominant Format, Especially for Club- and DJ-Oriented Releases

Verdict: partially supported.

Vinyl dominance is clearly supported: 26,940 of 29,926 releases, approximately 90.02% of the total. Its annual share also remained above 84% throughout the period.

However, the analysis did not establish a specific club- or DJ-oriented release classification. That component remains untested.

## 3. House, Deep House, Garage House, Techno, and Progressive House Accounted for a Substantial Share of Production

Verdict: partially supported; the five styles did not carry equal weight.

Annual evolution confirms particularly high House and Techno presence. House appears in approximately 57% of 1990 releases and 31% in 2000; Techno reaches around 47% in 1991–1992.

Progressive House expands from approximately 1% initially to 18% in 2000. Deep House and Garage House have smaller shares.

The hypothesis is better supported as a combination of high-volume styles and others with more limited presence, not equivalent dominance by all five.

I did not calculate their combined concentration without duplicates: percentages must not be added because a release may contain multiple style labels.

## 4. Certain Labels Were Particularly Active, Such as Strictly Rhythm, Nervous Records, Network Records, Cutting Records, FFRR, Deconstruction, Positiva, and Perfecto

Verdict: partially supported for the proposed selection.

The ranking confirms the activity of some proposed labels: FFRR had 185 releases, Strictly Rhythm 179, and Deconstruction 115. The overall leaders, however, were Virgin with 315, Epic with 263, and Columbia with 245—the more mainstream labels with a strong presence across markets.

Some initial examples therefore stand out but do not lead. This summary does not provide individual counts for the other five proposed labels, so the full list cannot be confirmed.

`Not On Label` remains in the data but is not interpreted as a single record company or included in the identified-label ranking.

## 5. More-Wanted Releases May Have Higher Median Prices

Verdict: descriptively supported.

[want] and [median_price_clean] had a Pearson correlation of 0.600 across 29,414 valid pairs.

This supports a positive linear association between recorded demand and median price within the sample. It does not mean every more-wanted release is more expensive or that demand causes price.

## 6. Average Rating May Relate to Collection Interest, Though Not Necessarily to Market Price

Verdict: partially supported and qualified by the findings.

The coefficients were:

| Relationship | Pearson correlation | Valid pairs |
|---|---:|---:|
| [average_rating_clean] and [have] | 0.174 | 29,132 |
| [average_rating_clean] and [want] | 0.276 | 29,192 |
| [average_rating_clean] and [median_price_clean] | 0.271 | 28,903 |

Ratings have a very weak positive association with ownership and weak positive associations with demand and price.

It is therefore inappropriate to conclude that ratings relate to ownership but not to price: both relationships are positive, and the price coefficient is numerically larger than that for [have].

Comparisons between coefficients are descriptive, use different samples, and were not formally tested for differences.

## 7. The United States, United Kingdom, Germany, Italy, Netherlands, and France Accounted for a Large Share of Production

Verdict: supported within the dataset, with substantial country differences.

Together, the six countries account for 24,803 of 29,926 records, approximately 82.88% of the total. The United Kingdom and United States lead, followed by Germany and Italy; the Netherlands and France have smaller shares.

The concentration was not static: between 1990 and 2000, the United Kingdom rose from 30.39% to 35.27%, Germany from 7.46% to 14.98%, and France from 1.14% to 4.83%. The United States fell from 31.36% to 18.33%, and Italy from 8.42% to 4.51%.

The conclusion concerns release geography, not artist nationality, manufacturing location, or sales.

## Summary of Conclusions

The exploratory analysis supports a general expansion in releases from the early to mid-1990s, vinyl dominance, and high geographic concentration in the six proposed countries.

It also identifies substantial differences between styles and labels, qualifying the initial selections: not all proposed names held equivalent positions.

Recorded demand showed a positive association with median price. Average ratings had weaker relationships with ownership, demand, and price, without establishing causation.

Hypotheses are considered supported or partially supported only within the dataset's scope and applied criteria. Untested components remain explicit limitations, without expanding the analysis to address them in this version.

## Final Dashboard Implementation and Functional Checks of Slicers and Macro

## Data Import and Refresh

I imported `01_discogs_electronic.csv` through Data → Get Data (Power Query).

The processed worksheet used in calculations is `Discogs_electronic_processed.xlsm`.

When running Data → Refresh All, Excel displayed a warning about connecting to an external source. I identified the connection as the imported project CSV.

I decided not to include Refresh All in the filter-reset macro: source refresh and selection reset remain separate operations.

## YEAR Slicer and PivotCharts

It controls the PivotTables used by:

- [Releases by year]
- [Formats by year]
- [Selected styles by year]

The annual style-proportion table documented earlier remains a separate analysis. Its percentages, denominators, or ranges are not attributed to the final PivotChart without checking the series directly. The review confirms the latter's interactivity, not equivalence between the two blocks.

## Connecting YEAR to Style Counts

`Top 10 styles by release count` uses a normal aggregated style table, not a PivotTable directly. To transfer selected years into its calculations, I added an auxiliary PivotTable in `Analytics`, connected to the same YEAR slicer.

| Element | Location or function |
|---|---|
| Selected-year list | `Analytics!B44:B54` |
| Grand total in the observed layout | `Analytics!B55` |
| Source year column | `Discogs_electronic_processed!G:G` |
| Source style column | `Discogs_electronic_processed!I:I` (`styles_clean`) |
| New measure in the normal table | `Releases_selected_year` |
| First confirmed calculation cell | `Analytics!K11` |

The chart uses:

```excel
Values: =Analytics!$K$11:$K$20
Labels: =Analytics!$I$11:$I$20
```

## Top 10 Highest-Rated Releases: Two Implementations

## Auxiliary Analysis: `Top_rated_releases`

The auxiliary worksheet uses a fixed minimum of 500 ratings and sorts releases by descending score, using rating count as a tie-breaker. The findings in research question 9 refer to that selection.

In that analysis, Choice — *Acid Eiffel / How Do You Plead?*, on Fragile Records, leads with 4.82 and 771 ratings.

## Interactive Dashboard Chart

The review identified the following flow:

```text
PivotTable in Analytics
          ↓
Output block Analytics!CS12:CT22
          ↓
Top 10 highest rated releases dashboard chart
```

| Component | Observed configuration |
|---|---|
| Visible identification fields | [title] and [artist] |
| Rating-count measure | Maximum of [num_ratings], in CP |
| Score measure | Average of [average_rating_clean], in CQ |
| PivotTable filters | [votes_threshold] and [style_primary] |
| Output block | `Analytics!CS12:CT22` |
| Output labels | Column CS, [Artist - Title] |
| Output scores | Column CT |
| Checked reference | CT13's score comes from CQ13 |

The screenshots initially showed both filters set to “(All)”. In that view, 5.000 scores appeared alongside low rating counts in the PivotTable. The chart must therefore not be described as permanently restricted to releases with at least 500 ratings.

[style_primary] corresponds to the first style in [styles_clean]; it is not equivalent to searching for the style among all labels of a release.

## Testing the Votes Threshold Slicer

I selected only `500+` in the dashboard slicer and confirmed that Choice moved to first place.

The test shows that the filter reaches the final chart through its table and supporting block. The confirmation concerned Choice's first position; there was no independent check of all ten positions, the displayed score, or the chart's tie-breaker.

- The 500-rating minimum depends on selecting `500+`.
- Chart ties are resolved by rating count.
- The PivotTable displays an average of [average_rating_clean] and a maximum of [num_ratings]; these aggregations must not be confused with a rating-count-weighted average.
- Visible grouping by artist and title does not prove that all editions are separated by a unique identifier in this chart.

### Summary Text for the Report

To build the dashboard, I combined PivotTables, auxiliary tables, and Excel formulas. I connected YEAR to the annual release, format, and selected-style PivotCharts. To transfer temporal selections to style counts, I added an auxiliary PivotTable returning the selected years and added [Releases_selected_year] to the supporting table. I checked both multiple-year selection and the calculation's behavior. Automatic reordering of the top ten styles was also verified.

I retained the style PivotChart to preserve interactivity rather than replacing it with a static visualization with smoothed lines. I distinguished this chart from the auxiliary annual percentage analysis by style label.

For the highest-rated releases chart, I identified a PivotTable in `Analytics` and the `CS12:CT22` block supplying its labels and scores. I confirmed that selecting `500+` in `Votes threshold` places Choice first. I separated this interactive implementation from `Top_rated_releases`, which uses a fixed minimum of five hundred ratings and a rating-count tie-breaker.
