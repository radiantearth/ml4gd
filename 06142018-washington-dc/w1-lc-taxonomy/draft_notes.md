Participants:
Markus Walsh (MW), Senior Research Scientist, Selian Agricultural Research Institute
Christoph Aubrecht (CA), ESA Representative at WB, European Space Agency
Kevin Horn (KH), Ecosystem Ecologist / Remote Sensing Specialist, USAID
Murali Krishna Gumma (MKG), Remote Sensing and GIS Scientist, CGIAR
Tasso Azevedo (TA), Lead MapBiomas, MapBiomas
Matt Hansen (MH), Professor, University of Maryland
Yonah Bromberg Gaber (YBG), Platform Developer COmmunity Associate, Radiant.Earth


#### Day 1 Consensus point:

***Assertions***	
1. “Use” and “Cover” are two different class layers
	
	1.1. Every pixel has cover attributes
	
	1.2. Not every pixel has use attributes--always layered on top of cover

2. LCCS (LCCS_v3.0.pdf) makes a good first couple of dichotomous decisions - a type but not exact

	2.1. Build classes from defined attributes (Include Attributes vs just a class or legend class)

	2.1.1. Adapt to any type of legend you have in the country

3. Add contextual information through time and space
4. Certain Classes are temporally dependent
5. Not tied to any sensor
6. Geographic and thematic interests/scopes may change the taxonomy

***Questions for tomorrow***
1. What are the attributes?
2. What are the uses?
3. What are the physiognomic landforms?
4. How do attributes, uses, and landforms relate to each other?
5. ISO MUL/Standard around LCCS? (https://www.iso.org/standard/44342.html )


--------------------------------------



MW: Start by looking what's out there and deciding from there, Maybe start with FAO.
FAO LCCS "Cultivated and managed areas"
Start with Binary: Vegetative/Non-Vegetative, aquatic/non-acquatic,etc, then go into madular/hierarchical

Specifications: 10 m resolution of the map, then Categorical is okay

CA: CCI Land Cover has eight classes
Woodlands, shrublands, forest
"The legend includes 10 generic classes that appropriately describe the land surface at 20m: "trees cover areas", "shrubs cover areas", "grassland", "cropland", "vegetation aquatic or regularly flooded", "lichen and mosses / sparse vegetation", "bare areas", "built up areas", "snow and/or ice" and "open water"." (http://2016africalandcover20m.esrin.esa.int/ ) 

Wetlands/Watery shrubs are problematic, because it could be agriculture, etc. 
Instead, wetland is a separate hydrological structure

Aggregating up is part of it.

MH: The problem with mosaic classes is that they aren't useful, too broad/
MW: What about Savanna?
MH: It's true, that we could have classes that are distinctly defined for physionomic properties, like forest as 5 m tall and falling. 

## Level One: Primarily Vegetated/Primarily Non-Vegetated with a threshold of 4%

MF & MH: Map the life form and then map the use for terrestrial vegetation (Use as a separate)

What's a fallow field? What's the difference beteen Cultivated and (semi)natural vegetation

MW: It depends on use

TA: We have to make a distinction between a static class and a historically-influenced class, i.e. a forrestry region with repeated regrowth; Land Cover is static, Land Use is historical


MW: System of Environmental-Economic Accounting (SEEA) https://unstats.un.org/unsd/envaccounting/seearev/seea_cf_final_en.pdf (Annex 1.C, page 299)

## LCCS-like will allow for dichotmous and then mediated decisions, then adding in contexts for time and spatial proximity


L
Mark's commnet:
    - Who is the end user of the land cover map? That will inform land cover labels. 
    

-----------------------------------------------
*Day 2 Consensus
-----------------------------------------------

Assumption: The land cover will be classified Annually; some decisions are dependent upon a year-long curve or annual maximums.

Attributes
	* Percent vegetation cover
	* Percent Woody Cover
	* Vegetation Height
	* Percent of year that soil is sataurated
	* Elevation
	* Species
	* Artificial (Cultivated)/(Semi)Natural
	* Water/Bare Ground/Snow-Ice
	* Annual(Seasonal)/Perennial(Evergreen)
	* Broadleaf/Needleleaf

*Schema


Key: 
x = Threshold of minimum vegetation
y = Threshold of minimum woody cover
z = Threshold of minimum tall woody height
p = Highest density threshold
q = Highest sparse threshold
f = Soil saturation threshold
W = % Woody Cover
H = vegetation height
V = % Vegetation cover
S = % of year that soil is saturated
E = Elevation

Non-tree parameters:
	* Species
	* Elevation
	* Wetland
		* Yes (S > f)
		* No (S < f)

LC Tree: {Examples, with assumptions V = 10%, W = 10%, H = 5 m, }
	1. Bare (Max Veg Year V < x%)
		2. Water
			3. Artificial Water {Dam, Impoundment, Channeling, Swimming Pools}
			3. Natural Water {Ocean, River, Lake}
		2. Bare Ground
			3. Artificial {Buildings, Roads, Astroturf}
			3. Natural {Rock, Bare soil, Lava}
		2. Snow/Ice (Permanent)
	1. Vegetated (Max Veg Year V > x%)
		2. Woody (W > y% woody cover)
			3. Dense canopy cover (W > p)
				4. Tall (H > z meters) 
					5. Cultivated {Eucalyptus Plantation, Walnuts, Almonds, Teak}
					5. (Semi)Natural
						6. Broadleaf
							7. Seasonal {Miombo forest, Oak forest, Temperate deciduous forests, Chaco Woodland}
							7. Evergreen {Rainforest}
						6. Needleleaf
							7. Seasonal  {Larch}
							7. Evergreen {Pinelands, Spruce}
				4. Short (H < z meters)
					5. Cultivated {Citrus Orchard, apples, olives, tea}
					5. (Semi)Natural {Chaparral}
			3. Medium canopy cover (p > W > q)
				4. Tall (Max height >z meters
					5. Cultivated
					5. (Semi)Natural
						6. Broadleaf
							7. Seasonal
							7. Evergreen
						6. Needleleaf
							7. Seasonal
							7. Evergreen
				4. Short (Max height < z meters)
					5. Cultivated
					5. (Semi)Natural
			3. Sparse canopy cover (q > W > y
				4. Tall (Max height >z meters
					5. Cultivated
					5. (Semi)Natural
						6. Broadleaf
							7. Seasonal
							7. Evergreen
						6. Needleleaf
							7. Seasonal
							7. Evergreen
				4. Short (Max height < z meters)
					5. Cultivated
					5. (Semi)Natural
		2. Other (W < y% woody cover)
			3. Cultivated 
				4. Annual {Soybean, Maize, Wheat, Rice} 
				4. Perennial {Sugarcane}
			3. (Semi)Natural
				4. Annual {Annual Grasslands}
				4. Perennial {Perennial Grasslands, Lichen, Moss}

Some notes:
	- Designed to be the top level and translateable, so that refined details can be added in the cover classes.
	- Designed for Global use, and requires annual data to determine maximums.


-----------------------------------------------------

When it comes to metadata, particularly with temporal/spatial scale. Should that be included or not? 

## Attributes is okay to use

MW, MH: Distinguishing between land cover and land use is too impractical, requires too many attributes

https://github.com/ISO-TC211/GOM/tree/master/isotc211_GOM_harmonizedOntology/19144-2/2012

Top level: Vegetative or non-vegetative (Less than 10%)

--
Collaborate seamlessly on documents! This pad text is synchronized as you type, so that everyone viewing this page sees the same text. 
Create your own board and a (secret) name for it here: http://board.net This service is provided on fair-use with open source technology by fairkom. 
Consider a donation in Euro or FairCoin https://www.fairkom.eu/en/sponsoring#Donations for disk space and new features. Virtual hug guaranteed! 

