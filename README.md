# census
A Python Script Provides access to ACS and SF1 data sets.
#### Steps :

1)Get  Census API key.

2) The get method is the core data access method on both the ACS and SF1 data sets.
By default, the year for a dataset is the most recent year available. To access earlier data, pass a year parameter to the API call:
The default year may also be set client-wide:

c = Census("MY_API_KEY", year=2010)
Detailed information about the API can be found at the Census Data API User Guide.



3) Not all geographies are supported in all years. Calling a convenience method with a year that is not supported will raise census.UnsupportedYearException.
Census API documentation for more geographies beyond the convenience methods.
4)ACS5 Geographies


state(fields, state_fips)
state_county(fields, state_fips, county_fips)
state_county_blockgroup(fields, state_fips, county_fips, blockgroup)
state_county_subdivision(fields, state_fips, county_fips, subdiv_fips)
state_county_tract(fields, state_fips, county_fips, tract)
state_place(fields, state_fips, place)
state_congressional_district(fields, state_fips, congressional_district)
state_legislative_district_upper(fields, state_fips, legislative_district)
state_legislative_district_lower(fields, state_fips, legislative_district)
us(fields)
state_zipcode(fields, state_fips, zip5)


#### Examples
The geographic name for all census tracts for county 170 in Alaska:

c.acs5.get('NAME', geo={'for': 'tract:*',
                       'in': 'state:{} county:170'.format(states.AK.fips)})
To get list of tables


c.acs5.tables()
