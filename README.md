# Case Study - An analysis of Beer and Breweries for Budweiser  

A review and analysis of beer and breweries by state. We will review missing data and how we filled it, number of breweries by state, summary statistics like medians and means of ABV and IBU at the beer level, and finally a review of the relationship between Ales, IPAs and other types of beer.
 
  
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

### Mean_Elevation_per_State.csv:  
#### &nbsp;&nbsp;&nbsp;&nbsp;51 state elevations and populations in all 50 states + DC  
  
&nbsp;&nbsp;&nbsp;&nbsp;Rank: Unique identifier of the state.  
&nbsp;&nbsp;&nbsp;&nbsp;State: The full name of each state.  
&nbsp;&nbsp;&nbsp;&nbsp;Population: The population for each state.  
&nbsp;&nbsp;&nbsp;&nbsp;State_Abr: The two letter abbreviation for the state.  
&nbsp;&nbsp;&nbsp;&nbsp;High point: The highest elevation for the state.  
&nbsp;&nbsp;&nbsp;&nbsp;Low point: The lowest elevation for the state.  
&nbsp;&nbsp;&nbsp;&nbsp;Mean elevationList by state: The mean elevation for the entirety of the state.  
  
  
## Overview of the analysis  
  
  
### Number of breweries per state  
|State	|Breweries	|State	|Breweries	|State	|Breweries	|State	|Breweries	|State	|Breweries	|
|-------|-----------|-------|-----------|-------|-----------|-------|-----------|-------|-----------|
|AK   	| 7         |HI 	  | 4         |ME 	  | 9         |NJ 	  | 3         |SD 	  | 1         |
|AK   	| 7         |HI 	  | 4         |ME 	  | 9         |NJ 	  | 3         |SD 	  | 1         |
|AL   	| 3         |IA 	  | 5         |MI 	  |32         |NM 	  | 4         |TN 	  | 3         |
|AR   	| 2         |ID   	| 5         |MN 	  |12         |NV   	| 2         |TX   	|28         |
|AZ   	|11         |IL   	|18         |MO 	  | 9         |NY   	|16         |UT   	| 4         |
|CA     |39         |IN   	|22         |MS 	  | 2         |OH   	|15         |VA   	|16         |
|CO   	|47         |KS   	| 3         |MT 	  | 9         |OK   	| 6         |VT   	|10         |
|CT   	| 8         |KY 	  | 4         |NC 	  |19         |OR 	  |29         |WA   	|23         |
|DC   	| 1         |LA   	| 5         |ND 	  | 1         |PA   	|25         |WI   	|20         |
|DE   	| 2         |MA    	|23         |NE     | 5         |RI    	| 5         |WV   	| 1         |
|FL   	|15         |MD   	| 7         |NH 	  | 3         |SC   	| 4         |WY   	| 4         |
|GA   	| 7         |	     	|			      |		    |			      |		    |			      |		    |		      	|
  
  
### Verifying the join between beer and brewery (head and tail)  
|Brewery_ID |Brewery_Name 					|Beer_ID|Beer_Name    				|City		 	|State	|ABV 	|IBU	|Style 									|Oz|
|-----------|-------------------------------|-------|---------------------------|---------------|-------|-------|-------|---------------------------------------|--|
|1 			|NorthGate Brewing  			|2692  	|Get Together 				|Minneapolis	|MN 	|0.045 	|50		|American IPA 							|16|
|1 			|NorthGate Brewing  			|2691 	|Maggie's Leap				|Minneapolis 	|MN 	|0.049 	|26     |Milk / Sweet Stout 					|16|
|1 			|NorthGate Brewing  			|2690   |Wall's End 				|Minneapolis    |MN 	|0.048 	|19     |English Brown Ale 						|16|
|1 			|NorthGate Brewing  			|2689   |Pumpion 					|Minneapolis    |MN 	|0.060 	|38     |Pumpkin Ale 							|16|
|1 			|NorthGate Brewing  			|2688   |Stronghold 				|Minneapolis    |MN 	|0.060 	|25     |American Porter 						|16|
  
  
|Brewery_ID |Brewery_Name 					|Beer_ID|Beer_Name          		|City 			|State  |ABV 	|IBU    |Style 									|Oz|
|-----------|-------------------------------|-------|---------------------------|---------------|-------|-------|-------|---------------------------------------|--|
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
&nbsp;&nbsp;&nbsp;&nbsp;Reviewing the first 5 records of summary_df for Median ABV and IBU per state.
|State|Median_ABV|Median_IBU| median_ABV.scaled|median_IBU.scaled|
|-----|----------|----------|------------------|-----------------|
|AK   |0.056     |34.0      |0.006867089       |0.02227067       |
|AL   |0.060     |39.5      |0.940791179       |0.71637307       |
|AR   |0.052     |36.0      |-0.927057001      |0.27467154       |
|AZ   |0.057     |22.0      |0.240348111       |0.77947329       |
|CA   |0.058     |40.0      |0.473829134       |-1.49213459      |
  
  
### Max ABV and IBU by state  
&nbsp;&nbsp;&nbsp;&nbsp;Reviewing the first 5 records of summary_df for Max ABV and IBU per state.
|State|Max_ABV|Max_IBU| max_ABV.scaled| max_IBU.scaled|
|-----|-------|-------|---------------|---------------|
|AK   |0.068  |71     |-1.4023857     |-1.1581394     |
|AL   |0.093  |103    |0.2702446      |0.4235204      |
|AR   |0.061  |46     |-1.8707222     |-2.3938111     |
|AZ   |0.095  |99     |0.6716758      |1.0166429      |
|CA   |0.099  |115    |0.4040550      |0.2258130      |
  
  
### Summary statistics and distribution of the ABV variable  
Here we found that most of the beers fell within a normal distribution with most beers generally being somewhat equal in its 
alcoholic content. One thing to note in particular was how many beers hover around the .05 ABV. This could be due to state laws or consumers' taste for moderate alcohol content in their beer. We used a density mapped histogram.  

  
### Relationship between ABV and IBU  
We do see a positive,moderate correlation between ABV and IBU with r value of .57; the projeced IBU increases as ABV increases to some degree. It's estimated that about 32.55% of the variation of a beer's bitterness can be attributed to how much alcohol the beer has. We used correlation, scotterplot, and histograms to assess the relationship.  
  
  
### Classifying beer styles based on IBU as IPA, Ale, or Other  
When using a KNN model, we can project a beer's predicted style just by reviewing its IBU with approximately 71.91% accuracy. With regards to IBU alone, identifying the beer's style as IPA is much easier than Ales or Other.  
  
  
### Additional analysis to review the population and per capita brewies and beers by state  
With Colorade leading the states in total number of breweries, it has 8.5 breweries per 1M adults over the age of 21. Only Vermont, Alaska, and Montana rank ahead of Colorado in breweries per capita. Note that Vermont, Alaska, and Montana are all low population states. When looking for a place to build a new brewery, we can see two advantages - moving into states with high population and high per capita breweries, or high population and low per capita breweries. For the first option, there will be stiff competition, but a beer thirsty population and often times beer destination, whereas with the second option, you could establish a market with little or no competition that could eventually become a beer attraction.  
