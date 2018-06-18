### Questions for WG 2

1.	How to improve the quality/quantity of training data? (How do we quantify tradeoff?)

2.	What should be the metric for measuring training and testing data diversity? (How do decide splits?)

3.	How to achieve higher accuracies within each class, and between different classes?

4.	(How do we balance local, national, regional, global performance for global LCLU?)

5.	(How do you choose loss functions that relate class similarities to wrongness?)

### Questions for WG 3 

1.	How do you maintain datasets across time and space for change tracking #WG3?

2.	How do we track data provenance over the course of training (data, labels) #WG3?

### Definitions
- Stat vs. ML
- Traditional methods (feature engineering) vs. DL (none)
- White box vs. black box

1. How to improve the quality/quantity of training data? (How do we quantify tradeoff?)
- minimum standard information
  - metadata/provenance
  - contributor
  - method - image, ground
  - date of sample, labeling
  - location (bounding box)
  - Assumption that training data is derived from someone interpreting satellite image, which could be different from on-the-ground.
  - spatial scale
  - temporal scale
  - quality/confidence (of worker)
- quantity questions
  - which existing sources can be brought in? (photoquest, geowiki, AfSIS, OSM, ...)
  - filtered to comply with quality criteria
  - communicate standards to improve quality

Framework for ML
- Situation on the ground - want to do something, based on analysis.
- Ground truth as source data: Landsat/Sentinel.
- Source data error: out of date, cloudy, not representative of ground truth.
- Model: source data --> prediction.
- Believe model bc representative of source data. Test data MUST be representative of source data.
- Model error: run model on sample believed to be true, some bound of model error based on labels.
- Information error: source data doesn't align with problem, resolution of data or problem specification.
- Machine learning model: training data (should be related to source data) interacts with validation data (should look a lot like test data).
- Ground to action chain as accurate as possible.

2. What should be the metric for measuring training and testing data diversity? (How do decide splits?)
- class dependent representiveness
  - geographical/regional (intraclass variety)
  - spatially/temporally scaled, by class 
  - starting point: assess against existing LC maps
  - https://developmentseed.org/blog/2018/03/19/geo-diversity/
