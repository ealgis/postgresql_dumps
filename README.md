# EALGIS Data Loader: PostgreSQL Dumps

PostgreSQL database dumps generated from EALGIS's data loaders.

Download the dump files from below and restore them into your database.

## Data Loaders

-   [2016 Census](https://github.com/ealgis/aus-census-2016)
-   [2011 Census](https://github.com/ealgis/aus-census-2011)
-   [Australian Electorates](https://github.com/ealgis/australian-electorates)
-   [Australian Statistical Geography Standard](https://github.com/ealgis/asgs)
-   [Generic CSV Loader](https://github.com/ealgis/generic-csv-loader)

## Pre-requisites

-   PostgreSQL 10+ with PostGIS 2.4+
-   A knowledge of [Postgres pg_restore parameters](http://www.postgresql.org/docs/9.5/static/app-pgrestore.html)

## Dumps

These dumps come from PostgreSQL 10.7 and PostGIS 2.5.

**2016 Census**

-   [Aboriginal and Torres Strait Islander Peoples Profile](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/aus_census_2016/aus_census_2016_atsip.dump) (~19MB)
-   [General Community Profile](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/aus_census_2016/aus_census_2016_gcp.dump) (~512MB)
-   [Place of Enumeration Profile](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/aus_census_2016/aus_census_2016_pep.dump) (~357MB)
-   [Time Series Profile](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/aus_census_2016/aus_census_2016_tsp.dump) (~62MB)
-   [Working Population Profile](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/aus_census_2016/aus_census_2016_wpp.dump) (~35MB)
-   [ASGS Geometry](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/aus_census_2016/aus_census_2016_shapes.dump) (~1.6GB)

**2011 Census**

-   [Basic Community Profile](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/aus_census_2011/aus_census_2011_bcp.dump) (~335MB)
-   [Indigenous Profile](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/aus_census_2011/aus_census_2011_ip.dump) (~23MB)
-   [Place of Enumeration Profile](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/aus_census_2011/aus_census_2011_pep.dump) (~334MB)
-   [Time Series Profile](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/aus_census_2011/aus_census_2011_tsp.dump) (~79MB)
-   [Working Population Profile](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/aus_census_2011/aus_census_2011_wpp.dump) (~32MB)
-   [Extended Community Profile](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/aus_census_2011/aus_census_2011_xcp.dump) (~59MB)
-   [ASGS Geometry](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/aus_census_2011/aus_census_2011_shapes.dump) (~2.7GB)

**Australian Electorates**

-   [Federal](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/australian-electorates/au_federal_electorate_boundaries.dump) (~587MB)
-   [NSW](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/australian-electorates/au_nsw_state_electorate_boundaries.dump) (~30MB)
-   [NT](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/australian-electorates/au_nt_state_electorate_boundaries.dump) (~1MB)
-   [QLD](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/australian-electorates/au_qld_state_electorate_boundaries.dump) (~20MB)
-   [SA](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/australian-electorates/au_sa_state_electorate_boundaries.dump) (~29MB)
-   [VIC](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/australian-electorates/au_vic_state_electorate_boundaries.dump) (~64MB)
-   [WA](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/australian-electorates/au_wa_state_electorate_boundaries.dump) (~73MB)

**Australian Statistical Geography Standard**

-   [ASGS Geometry 2011](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/asgs/asgs_2011_boundaries.dump) (~1.3GB)
-   [ASGS Geometry 2012](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/asgs/asgs_2012_boundaries.dump) (~248MB)
-   [ASGS Geometry 2013](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/asgs/asgs_2013_boundaries.dump) (~364MB)
-   [ASGS Geometry 2014](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/asgs/asgs_2014_boundaries.dump) (~251MB)
-   [ASGS Geometry 2015](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/asgs/asgs_2015_boundaries.dump) (~251MB)
-   [ASGS Geometry 2016](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/asgs/asgs_2016_boundaries.dump) (~1.4GB)
-   [ASGS Geometry 2017](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/asgs/asgs_2017_boundaries.dump) (~403MB)
-   [ASGS Geometry 2018](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/asgs/asgs_2018_boundaries.dump) (~402MB)
-   [ASGS Geometry 2019](https://s3-ap-southeast-2.amazonaws.com/ealgis/dumps/asgs/asgs_2019_boundaries.dump) (~153MB)

## Process

1. Download one or more set of dumps
2. Run `pg_restore` for each dump e.g. `pg_restore --host=localhost --username=postgres --dbname=your-database-name /path/to/your/folder/dumps/aus_census_2016_gcp.dump` and enjoy!
3. Run `VACUUM ANALYZE` on each of the database schemas that were loaded (e.g. aus_census_2016_gcp, aus_census_2016_pep)

### Data Licenses

Incorporates or developed using Census data from the Australian Bureau of Statistics under [Creative Commons Attribution 4.0 International licence (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

Incorporates or developed using Australian Statistical Geography Standard data from the Australian Bureau of Statistics under [Creative Commons Attribution 4.0 International licence (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

Incorporates data from Australian federal and state electoral commissions. Refer to [Australian Electorates](https://github.com/ealgis/australian-electorates).

## Data Customisation

Census metadata files have been customised to fix some of their known minor limitations. The most notable are:

-   ABS metadata statements have been parsed through our data loaders to turn the provided XLS files into a queryable JSON structure. As always, please refer back to the source metadata.
