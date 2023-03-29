# OpenElections Data Repository Specs

## Repository

There should be 52 repositories for data, with the url of the form `https://github.com/openelections/openelections-data-CODE` where `CODE` can be:
 * One of the 50 state postal abbeviations (lower-case)
 * `dc` (for the District of Columbia)
 * `us` (for national results)

|Repositories |||||
|--|--|--|--|--|
[Alabama](https://github.com/openelections/openelections-data-AL) | [Alaska](https://github.com/openelections/openelections-data-AK) | [Arizona](https://github.com/openelections/openelections-data-AZ) | [Arkansas](https://github.com/openelections/openelections-data-AR) |[California](https://github.com/openelections/openelections-data-CA)
[Colorado](https://github.com/openelections/openelections-data-CO) | [Connecticut](https://github.com/openelections/openelections-data-CT) | [Delaware](https://github.com/openelections/openelections-data-DE) | [Florida](https://github.com/openelections/openelections-data-FL) | [Georgia](https://github.com/openelections/openelections-data-GA)
[Hawaii](https://github.com/openelections/openelections-data-HI) | [Idaho](https://github.com/openelections/openelections-data-ID) | [Illinois](https://github.com/openelections/openelections-data-IL) | [Indiana](https://github.com/openelections/openelections-data-IN) | [Iowa](https://github.com/openelections/openelections-data-IA)
[Kansas](https://github.com/openelections/openelections-data-KS) | [Kentucky](https://github.com/openelections/openelections-data-KY) | [Louisiana](https://github.com/openelections/openelections-data-LA) | [Maine](https://github.com/openelections/openelections-data-ME) | [Maryland](https://github.com/openelections/openelections-data-MD)
[Massachusetts](https://github.com/openelections/openelections-data-MA) | [Michigan](https://github.com/openelections/openelections-data-MI) | [Minnesota](https://github.com/openelections/openelections-data-MN) | [Mississippi](https://github.com/openelections/openelections-data-MS) | [Missouri](https://github.com/openelections/openelections-data-MO)
[Montana](https://github.com/openelections/openelections-data-MT) | [Nebraska](https://github.com/openelections/openelections-data-NE) | [Nevada](https://github.com/openelections/openelections-data-NV) | [New Hampshire](https://github.com/openelections/openelections-data-NH) | [New Jersey](https://github.com/openelections/openelections-data-NJ)
[New Mexico](https://github.com/openelections/openelections-data-NM) | [New York](https://github.com/openelections/openelections-data-NY) | [North Carolina](https://github.com/openelections/openelections-data-NC) | [North Dakota](https://github.com/openelections/openelections-data-ND) | [Ohio](https://github.com/openelections/openelections-data-OH)
[Oklahoma](https://github.com/openelections/openelections-data-OK) | [Oregon](https://github.com/openelections/openelections-data-OR) | [Pennsylvania](https://github.com/openelections/openelections-data-PA) | [Rhode Island](https://github.com/openelections/openelections-data-RI) | [South Carolina](https://github.com/openelections/openelections-data-SC)
[South Dakota](https://github.com/openelections/openelections-data-SD) | [Tennessee](https://github.com/openelections/openelections-data-TN) | [Texas](https://github.com/openelections/openelections-data-TX) | [Utah](https://github.com/openelections/openelections-data-UT) | [Vermont](https://github.com/openelections/openelections-data-VT)
[Virginia](https://github.com/openelections/openelections-data-VA) | [Washington](https://github.com/openelections/openelections-data-WA) | [West Virginia](https://github.com/openelections/openelections-data-WV) | [Wisconsin](https://github.com/openelections/openelections-data-WI) | [Wyoming](https://github.com/openelections/openelections-data-WY)
[District of Columbia](https://github.com/openelections/openelections-data-DC) | [United States](https://github.com/openelections/openelections-data-US) |

## Filenames
The root of the repository should contain folders with the four digit year for each election.

Election results should be placed in a csv file for statewide results with a filename following the pattern: `$YEAR/$YEAR$MONTH$DAY__$STATE__$ELECTIONNAME__$BREAKDOWN.csv` where
 * `$YEAR` is the four digit year of the election
 * `$MONTH` is the two digit month of the election
 * `$DAY` is the two digit day of the election
 * `$STATE` is the two letter state abbreviation (lower-case)
 * `$ELECTIONNAME` is the election "name"
 * `$BREAKDOWN` is how the results are broken down, either `county` or `precinct`

The county-specific data should be in a csv file with the filename `$YEAR/counties/$YEAR$MONTH$DAY__$STATE__$ELECTIONNAME__$COUNTY__$BREAKDOWN.csv` where
 * `$COUNTY` is the full name of the county in all lower-case.

## CSV Format
Each csv should be comma delineated (not tabs). The first row should specify which fields are present. Here are the expected fields and whether the column is required (which does not necessarily mean that the field has a value defined for every row).

 * **Region Fields**
   * `county` (string) *required*
   * `precinct` (string) *required for county-specific results*
 * **Election Fields**
   * `office` (string) *required*
   * `district` (int) *required*
   * `party` (string) *required*
   * `candidate` (string) *required*
 * **Count Fields** (int type for all)
   * `votes` *required*
   * Optional Vote Types, including
     * `election_day`
     * `provisional`
     * `early_voting`
     * `absentee`
     * `advance_in_person`
