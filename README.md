# Coursera_Capstone
This repository will be mainly used for the IBM capstone project.
Purpose: 
Data scrapping of Neighborhoods in Toronto and using foursquare API to understand venues within each neighborhood. 
We then do a cluster analysis to understand different characteristics of each Neighborhood based on venues present.

Some tools/libraries used: 
1. website scraping using Beautifulsoup
2. json and json_normalize to help normalize and handle json files
3. geopy to geolocate for mapping purposes
4. sklearn to do our cluster analysis
5. folium and matplotlib  to visualize clusters on a map

# Final Project
This final project is based on data Analysis of where a business should open a coffee shop. 

## Intro
1.	Problem & background: Someone is looking to open a coffee shop in Toronto and needs a recomendation on where they can open, based on competition, location to foot traffic,and population.
2.	Data & usage: We will use a number of different data sources to explore neighborhoods and postal codes.
a) 2016 population census Canada for population: https://www12.statcan.gc.ca/census-recensement/2016/dp-pd/hlt-fst/pd-pl/Tables/File.cfm?T=1201&SR=1&RPP=9999&PR=0&CMA=0&CSD=0&S=22&O=A&Lang=Eng&OFT=CSV
b) postal codes and their neighborhoods: https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M
c) foursqure data API (foursquare developer credentials required)
3.	Assumptions:
a) Venues that are not coffee shops (e.g. parks, businesses, restaurants), create good foot traffic for coffee shops
b) Coffee shops within the same Postcode are bad for traffic as it is competition
c) A % of the Population of that Postcode will be considered foot traffic for that coffee shop

## Methodology
1.	We collected Data of Toronto Neighborhoods by postal code, and population by postal code.
2.	We then enriched the data with all venues within 500 metre radius of that postal code.
3.	We also enriched our data by categorizing all Coffee shopes within that zip code.
4.	We attributed an estimated foot traffic to our coffee shope by: a) total population of Toronto/Total venue/ Total coffeeshops of the postal code in Toronto *1% (this is an estimate of how much foot traffic we would get as a result of nearby venues(e.g. parks, schools, restaurants) b) Total population of the postal code/ Total cofeeshops of the postal code *1%
5.	We used a cluster analysis to group each postal code by lowest to highest total foot traffic
