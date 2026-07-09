# Bulgarian Elections Abroad Analysis

Bulgarians have voted in eight parliamentary elections since 2021. The most recent election was held in April 2026. Two months earlier, Parliament changed the rules for voting abroad.

The new rules limit the number of polling stations that can be opened in countries outside the European Union to **20**, in addition to those located at embassies. Bulgarian law does not allow citizens to vote by post or electronically, leaving Bulgarians living abroad with no option other than voting in person.

The goal of this analysis is to quantify the impact of this change.

It compares the **October 2024** and **April 2026** parliamentary elections using polling station and voting data published by Bulgaria's Central Election Commission (CEC): https://results.cik.bg/

The key finding is that after the new limit was introduced, **17,578 fewer people voted in Turkey** than in the previous parliamentary election. This is consistent with election experts' warnings that limiting the number of polling stations abroad could discourage voter participation.

## Polling Station Data

The raw datasets contain one row for each polling station abroad.

The first step of the analysis was to compare the number of polling stations in each country in 2024 and 2026 to identify which countries were affected. The Pandas library was used for this part of the analysis. The results showed that Turkey, the UK, and the US were the only countries outside the EU with more than 20 polling stations in 2024. As a result, the analysis focuses on these three countries.

The second step was to map the polling stations in 2024 and 2026 to visualize the differences. The 2026 dataset includes the latitude and longitude of each polling station, making it possible to map them directly. The 2024 dataset does not include coordinates but does contain addresses, which were geocoded using Geocoder.

The resulting CSV files were then converted to GeoJSON using geojson.io, and the maps were created with Datawrapper.

## Voting Data

The raw datasets also contain voting data. In this analysis, the number of voters is based on the signatures in polling station voter lists published by the CEC. Because Bulgaria does not maintain a register of eligible voters living abroad, voter turnout cannot be calculated.

The main step in this part of the analysis was to calculate the number of voters in each of the three countries in 2024 and 2026. The Pandas library was used for this analysis. The results were saved to a new DataFrame and visualized in a bar chart.

For context, the total number of Bulgarian voters who voted abroad was also calculated. The results showed that more people voted abroad in 2026 than in 2024. This was also true in both the UK and the US, despite the reduced number of polling stations.

However, 17,578 fewer people voted in Turkey. This finding is consistent with election experts' warnings that limiting the number of polling stations abroad could discourage voter participation.

