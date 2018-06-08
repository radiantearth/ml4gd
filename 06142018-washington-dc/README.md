# Machine Learning for Global Land Cover Classification

Radiant.Earth is hosting a 2 day technical workshop 14-15 June, 2018 in Washington, D.C. Goal is to discuss and develop specifications for the global LC labeled training dataset by aggregating inputs from all participants. 

## Expected Outcomes:
 * Generating an inclusive hierarchical taxonomy of LC classes at global scale;
 * Defining specifications of the signature library for labeling and metadata storage;
 * Reviewing, examining and documenting best practices for using ML with satellite imagery for LC classification; and
 * Identifying knowledge gaps.


## Participants:
Full list of participants is available [here](participants.md). Each participant is assigned to a working group.



## Workshop Structure

To achieve the goals of this meeting, three topic-specific working groups will address the following during the breakout sessions:

 * **Working Group 1: Land Cover Taxonomy**

This group focuses on developing the hierarchical LC class taxonomy. Participants will use current taxonomies as a baseline and develop the globally inclusive LC class taxonomy which has a hierarchical structure. The purpose of this groups is to document a LC taxonomy that would allow using satellite/airborne observations with different Ground Sampling Distances (GSD) and generate LC labels which could be validated/evaluated against other products with different GSD. A non- inclusive list of the topics to be discussed:

1. How many levels would be necessary for the hierarchical taxonomy? 

2. How to relate those levels to specific GSD?

3. What should be the land cover classes on each level?

4. How to allow new classes that might emerge in future be included in the taxonomy?

(Additional topics may emerge from the morning session).


* **Working Group 2: Machine Learning Algorithms**

This group will review and document best practices in using ML for LC classification. A non- inclusive list of the topics to be discussed:
	
1. How to achieve higher accuracies within each class, and between different classes?
 	
2. What should be the metric for measuring training data diversity?
 
3. How to improve the quality of training data?

(Additional topics may emerge from the morning session).


* **Working Group 3: Training data specifications**

This group will develop specifications for LC labels to be stored in the imagery metadata. The goal would be to use the Spatio-Temporal Asset Catalogue (STAC) for this purpose, and design specifications for labels to be stored in imagery with Cloud-Optimized Geotiff (COG) format. A non- inclusive list of the topics to be discussed:

1. How to store labels and any parameters associated with those (such as uncertainty) in COG format?

2. How to incorporate the LC taxonomy level (from WG 1) into the metadata? 

(Additional topics may emerge from the morning session).


