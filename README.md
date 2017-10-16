# BHL-content_analysis

Collection of scripts used to perform content analysis on the [Biodiversity Heritage Library](www.biodiversitylibrary.org) (BHL) collection in 2017. This project was a part of the National Digital Stewardship Residency (NDSR) program. 

## Temporal representation
1 python script dates(title_item.py)

To graph every item in BHL by year, I downloaded the title and item tables from [BHL export page.](http://biodivlib.wikispaces.com/Data+Exports) I edited title table down to the following fields: titleid, startyear, endyear, and call number. I edited down item table to the following fields: titleid, itemid, year, and volumeinfo. 

These two edited down tables are merged together using title_item.py script. 
Years are assigned to each item. If multiple years are available for an item (ex. startyear and endyear), a range was given to an item and divided by the weight of the range (ex. startyear =1900 and endyear =1904, range =4 years, item weighted as 1/4 of an item for each year). 

title_item.py then graphs the items by year using matplotlib. 

## Taxonomic representation
3 python scripts

Download zip of all tables from BHL export page, pagename file contains list of all scientific names found in BHL with their corresponding pageid. 

Use (test[taxon count])test.py to create a dictionary of every unique scientific name from BHL with a count of everytime it is found.

Use split2.py(**i think**) to split files into smaller files. Feed smaller files into http://listresolver.globalnames.org/ and select a data source to compare names to. (I used Catalog of Life). 

Using classification path results, filter names into different kingdoms using name_analysis.py script. Get rid of names that have no match, get rid of duplicates, find kingdom level of classification paths, count unique representation of kingdoms and total representation of kingdoms. 

## Geographic representation 
