Chris:  - What is the format we put the data in?

- What is the basic/minimum fields to include?

- It will be basic, but required to make it adoptable.

David G: Do we want to have Data with labels? or with vectors? What is exactly training data?

Rob: 	At Azavea raster vision has training chips separate from imagery, and then combines them and chips them. They live in separate places. 

	Decision to make - does it make sense to have a copy of the image and here's the training data. 

	Or have a trained item point at a particular image.

Drew: 	For this task we won't be doing object dection - won't have polygon pointing back at image. 

Rob: 	Lablemaker - the mask is derived from vector.

		Landcover / landclass will not be object based, and may not even be neural net.

		Naive first pass - here is an image, here is a labeled array - matching hierarchy that people come up with.

		- Is that derived from what's stored in the stack? Or do we do derivation first? 

David: 	If you're trying to do a geospatial thing the imagery is not the thing. Not matched to a specific image - how do you solve the problem.

  		- pre-chipping, 2012 national land classification - what would base level be of representing that as a standard to let people apply S1, S2, DG, Planet.

		- base level is 'here is representation of truth' - valid for specific length of time, trust for X length of time. Here's how we labeled it, this is what the classes mean. Start there.

		- Geospatial file of some sort. What is area that is actually labeled. If you naively apply to north america - you need to know where to clip it to. 

Drew: 	Point about using different providers. This project is going to be sentinel based. 

		- is labeled data stored separately or derived from 'truth' (A version of OSM).

David: 	Think of a tile server world - define vector, as people use it create a 'cache'. 

		- creation of tile set takes time. You can tile it on your way, not holden to any specific ways

Rob: 	WFS with valid dates - do it on the fly 'give me label chips for everything in this area'. 

Hamed: 	If we can make that connection we can do that separately. Time should be recorded.

		- David: that is 'source' - how did I get this label?


Two different types - wfs and tile services (raster). But even land class is 'feature' based.

Have exact time stamp of where you saw that. Can use composite imagery (6 month composite). 

Dynamic data like crop - can be different. 

WIth revisit hierarchy gets deeper - crop levels, 'early wheat' vs 'late wheat'. 

Discussion of data that is 'true' because it was gathered on the ground. 

Set up things like WFS / Raster Services, but at some point still look at data in some form against an image, so store at that point. This was verified at this time at this image by this user. 

Core thing is a raster plus a verified.

What does it mean for the crowd to do image segmentation label? 

David: 	Argue against rasterize vector data for the 'truth'. 

	Who has clicked pixels? No one wants to admit it. QGIS as points. Drew has a shoddy 'paint' thing. 
		
		- Could be extracted as polygon. 
		
		- get in to pixel / gsd questions.

How many times have you relabeled the same dataset. David 'I've traced boats of panama 4 times, off of three images' - point, to length, to width. Nothing worse than finding a data set that is 'almost' good enough. Getting the data set wrong is costly. 

Training dataset is 'just a vector representation' with a time stamp at a point in time. 

		- Drew - if you have that but it doesn't map to any image then it's not useful for training an algorithm.

Ground truth vs 'training data'. Ground truth is 'real', and training data is that matched to a time. 

Drew: 	Another problem - if we're doing polygons - how do we handle them overlapping (or empty spaces). Make a background class and drop on top of it. Raster case you'd have every thing labeled. ISPRS had 'clutter' for things that aren't there. 

Between ground truth and training data - if you are making training data for a use case that doesn't have overlap that's where you differentiate. 

discussion of vector output - road example made recently that choses path on AI. 

Mask R-CNN - does segmentation, straight to vector. 

Much easier to go from vector to raster than from raster back to vector. 
	
	Format for the core vectors. The equivalent for COG. 
		- ideally be able to serve it up, but without needing a service. 
		- vector format ideally has a geospatial hash, and ideally time hash.
		- could do in vector tiles...
		- just hash by centroid.
		- gets complicated

Core probably needs to be geojson. and then run service on top for 'query'. Use athena for slower stuff. SNS to keep a more active thing up to date. 
	
Training data that runs is raster / raster.

Value in a 'static WFS', just set a collection thing. 

STAC asset of GeoJSON with all its associated geojson.

Need a third item in the training data set - raster image + vector data + area labeled in the COG. 
	- COuld be its own stac item with the footprint as the valid place. no need for a mask. 


	*CORE* 

A 'training data' is a STAC Item that has two required assets - the image that it is valid for and the geojson of the labels in it. 
	
There is a notion of 'ground truth' where the geojson comes from. 
	
Chips classification, will just be geojsons of boxes. 
	

	*Training Data Profile of STAC* 
		Two required assets - associating
•	
•	
•	Item Level:
•	Assets - 2 required, the 'image' and the 'labels'
•	Time - 
•	Link - a required 'image source' relation to the metadata (ideally stac)
•	Task: .
•	Validation Type: 'None', 'human', 'crowd', 'expert'.
•	Confidence
•	Error - 0-1
•	
•	Collection Level:
•	Confidence <string> - read up on the confidence.
•	
•	
•	Label Asset
•	- Label uncertainty
•	
•	(from group 2):
•	  * contributor
•	  * method (from image,, ground truth)
•	  * date (that the label was made)
•	  * location (just the json)
•	  * scale
•	  * quality / confidence (of the worker)
•	  * training / test / validation data level?
•	
•	publishing new versions of the labeled data? 
•	
•	Updating of training dataset
•	
•	Are COG's required?
•	 - should maybe not restrict all the way. LiDAR point cloud.
•	 - COG strongly recommended. 
•	 - But sometimes you can't go COG. Or I want it non ortho rectified. Need sensor model here. 
•	
•	PNG's that are usable in the main image page?
•	 - No, but generate with label maker.
•	 - local, link back to the geo world - is a tooling thing.
