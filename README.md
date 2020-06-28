# Case Study - An analysis of Beer and Breweries for Budweiser  
 
## Data Sources  
### Beers.csv:  
#### &nbsp;&nbsp;&nbsp;&nbsp;2,410 unique beers from 558 breweries  
  
&nbsp;&nbsp;&nbsp;&nbsp;Name: Name of the beer.  
&nbsp;&nbsp;&nbsp;&nbsp;Beer_ID: Unique identifier of the beer.  
&nbsp;&nbsp;&nbsp;&nbsp;ABV: Alcohol by volume of the beer.  
&nbsp;&nbsp;&nbsp;&nbsp;IBU: International Bitterness Units of the beer.  
&nbsp;&nbsp;&nbsp;&nbsp;Brewery_ID: Brewery id associated with the beer.  
&nbsp;&nbsp;&nbsp;&nbsp;Style: Style of the beer.  
&nbsp;&nbsp;&nbsp;&nbsp;Ounces: Ounces of beer.  

### Breweries.csv:  
#### &nbsp;&nbsp;&nbsp;&nbsp;558 unique breweries in all 50 states + DC  
  
&nbsp;&nbsp;&nbsp;&nbsp;Brew_ID: Unique identifier of the brewery.  
&nbsp;&nbsp;&nbsp;&nbsp;Name: Name of the brewery.  
&nbsp;&nbsp;&nbsp;&nbsp;City: City where the brewery is located.  
&nbsp;&nbsp;&nbsp;&nbsp;State: U.S. State where the brewery is located.  

## Overview of the analysis  

### Number of breweries per state  

### Verifying the join between beer and brewery (head and tail)  
|Brewery_ID |Brewery_Name 					|Beer_ID|Beer_Name    				|City		 	|State	|ABV 	|IBU	|Style 									|Oz|
|-----------|-------------------------------|-------|---------------------------|---------------|-------|-------|-------|---------------------------------------|--|
|1 			|NorthGate Brewing  			|2692  	|Get Together 				|Minneapolis	|MN 	|0.045 	|50		|American IPA 							|16|
|1 			|NorthGate Brewing  			|2691 	|Maggie's Leap				|Minneapolis 	|MN 	|0.049 	|26     |Milk / Sweet Stout 					|16|
|1 			|NorthGate Brewing  			|2690   |Wall's End 				|Minneapolis    |MN 	|0.048 	|19     |English Brown Ale 						|16|
|1 			|NorthGate Brewing  			|2689   |Pumpion 					|Minneapolis    |MN 	|0.060 	|38     |Pumpkin Ale 							|16|
|1 			|NorthGate Brewing  			|2688   |Stronghold 				|Minneapolis    |MN 	|0.060 	|25     |American Porter 						|16|
|1 			|NorthGate Brewing  			|2687   |Parapet ESB 				|Minneapolis    |MN 	|0.056 	|47 	|Extra Special / Strong Bitter (ESB) 	|16|  
  
|Brewery_ID |Brewery_Name 					|Beer_ID|Beer_Name          		|City 			|State  |ABV 	|IBU    |Style 									|Oz|
|-----------|-------------------------------|-------|---------------------------|---------------|-------|-------|-------|---------------------------------------|--|
|556        |Ukiah Brewing Company      	|98     |Pilsner Ukiah         		|Ukiah    		|CA 	|0.055  |34     |German Pilsener 						|12|
|557       	|Butternuts Beer and Ale      	|52  	|Heinnieweisse Weissebier 	|Garrattsville  |NY 	|0.049  |17     |Hefeweizen 							|12|
|557       	|Butternuts Beer and Ale      	|51     |Snapperhead IPA 			|Garrattsville  |NY 	|0.068  |67     |American IPA 							|12|
|557       	|Butternuts Beer and Ale      	|50     |Moo Thunder Stout 			|Garrattsville  |NY 	|0.049  |25     |Milk / Sweet Stout 					|12|
|557       	|Butternuts Beer and Ale      	|49     |Porkslap Pale Ale 			|Garrattsville  |NY 	|0.043  |44 	|American Pale Ale (APA) 				|12|
|558 		|Sleeping Lady Brewing Company  |30 	|Urban Wilderness Pale Ale  |Anchorage    	|AK 	|0.049  |31     |English Pale Ale 						|12|

### Address the missing values in each column 
&nbsp;&nbsp;&nbsp;&nbsp;IBU missing 41.7% of data  
&nbsp;&nbsp;&nbsp;&nbsp;ABV missing 2.57% of data  
&nbsp;&nbsp;&nbsp;&nbsp;All other data noted as complete  
&nbsp;&nbsp;&nbsp;&nbsp;Missing data was filled in using the average ABV and average IBU by beer style  

### Median ABV and IBU by state  

### Max ABV and IBU by state 

### Summary statistics and distribution of the ABV variable  

### Relationship between ABV and IBU  

