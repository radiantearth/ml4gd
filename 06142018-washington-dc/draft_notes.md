### Welcome

***Dan Lopez, CTO, Radiant.Earth***

- ask for access to platform, developed by Azavea, with data/raster pipelines, data from many sources exposed through many form factors
  - Chris Holmes: maturing spec offering, federated architecture
  - working on events, notifications, & streaming, Raster & Data APIs already out and documented
  - Code and use cases open source
- STAC: normalize metadata for 
  - federated & decentralized
  - push and pull metadata and archives
  - STAC: normalize metadata within and arhive structure
  - embed geotiffs in structured format, compute at source
  - ML pipelines to AI models
  - growing list of providers, example repo http://bit.ly/iserv-cog
  - locked up, static, not being used --> cog format
- COG
  - Chris is resident expert
  - combining COG and STAC to underly platforms
  - http://cog-validate.radiant.earth/html
- ML Hub
  - http://github.com/MLHubEarth
  - ML algs, training data, image chips, shared to the world community

### Workshop Overview and Expected Outcomes 

***Hamed Alemohammad, Lead Geospatial Data Scientist, Radiant.Earth***

- MLHub.Earth
  - repo for sharing OS algs, training data, specs, best practices of ML to EO
  - Radiant.Earth: bring to global dev, democratize, sharable, invite others to do the same
  - GH repo: interoperable data, so users know standards. easy, consumable
  - ML & cloud grade, v1 over several months
  - questions like how to store labels, parameters in COG format?
  - collaborative answers, lots of investment in questions, learn from experiences
- LC
  - first labeled training set
  - well-known problem
  - challenges: don't have dynamic map, fine spatial resolution for all classes, and global
  - tap into tech, ML techniques, and cloud computing
  - what is best training data? first question --> generating that labeled data set, OS
  - Sentinel-2 data at 10m resolution, best OS data, will be OS for others, also global
  - 2 phases: ML alg to sampled scenes, segment & crowdsource verification of labels
  - Sponsored by Schmidt Futures: philanthropic, sponsor whole venture
  - Lots of specs, parameters to choose
- ML for Global Development
  - ML-ready. unified data analytics system, same environment/cluster
  - adoptable, discoverable, understandable
  - interoperable: how can datasets be intercomparable to verify evaluation?
  - inclusive, diverse: global
  - community centric technical committee
  - not just specific to LC --> ML, crowdsourcing, storing training data & labels applies to any EO
- Improved Decision Making in Agriculture
  - tools and analytics for applying ML/EO data
  - Crop Suitability Index: API for normalized value of suitability of major crops at global scale (lat/lon or polygon as input)
  - Use of massive spectral data for monitoring crop health/productivity, beyond classifical optical indices
  - Develop labeled image library of major crops in Africa
  - get in touch if interested, or know interested parties
- Workshop challenges
  - Land Cover Taxonomy
   - 2014 paper, many taxonomies, inconsistencies --> how to compare
   - lots of effort in generating, but challenge in evaluation
   - different defs and resolutions (MODIS vs. Landsat)
   - goal: hierarchical taxonomy (see sample hierarchy, with GSD levels)
   - result: efficient for land cover maps with different data, better decisionmaking
  - ML Algorithm and crowdsourcing
  - fast maturation, in and out of community, evolving answers
   - how to improve inter/intra class accuracy?
   - how to evaluate accuracy, diversity?
- Drew's blog: https://developmentseed.org/blog/2018/03/19/geo-diversity/
- don't know distribution, want to sample to be representative
- transfer stat approaches to 3D images
  - how to assess and improve training label quality?
  - what are best NN/DL algorithms?
  - ML ready and cloud compatible training data spec
   - how to store labels, parameters (uncertainty) in COG?
   - how to incorporate LC taxonomy (WG1) into metadata?
   - how to use img metadata to sample representative set of tiles at global scale?
  - Let us know if there are other questions
- Logistics
  - http://bit.ly/ml-lc-dc
  - note taking on board.net, general and working group
  - slack group

### Plenary: Perspectives on Advancing LC Classifications for Machine Learning   

***Moderator: Anne Hale Miglarese (AHM), CEO, Radiant.Earth Speakers (15 min each):***

- GB of data for $28k in early 1990s
- inflection of cloud, new space, data science	
- RS around globe: hunger to connect over tech
- RE provides connective tissue, open data, standards, science
- Don't all know each other


***Tasso Azevedo (TA), Lead, MapBiomass***
- GHG primarily from LU vs. Energy, Industry, and Waste
- uncertainy on measurement
- good at forest to nonforest deforestation in Amazon since 80s
- don't really understand afterwards: agri vs. mining vs. cities, how much back to forest
- understand root causes of GHG
- Brazil 6th largest emittor
- change from tree cover change to land use change (matrix)
- few official maps for specific years (94, 02, 10)
- one map: 2 years, 90 people, $3 million (?)
- too expensive for time series
- our challenge: cheaper, faster, reliable historial annual LC/LU maps of Brazil
- tools for dissemniation, publich cloud platform for analysis
- number of orgs
- Landsat bc time series, pixel-by-pixel, 1 x 1.5 degree tiles (556 in Brazil), processing in Google Earth Engine
- classes: forests -> natural..., non-forest natural, farming, non-veg, water --> 4/5 additional classes in few months
- for each biomes (macro regions), one group: 1 person from RS, science, env
- cross cutting themes
- 1 map per class seperately, then stack with rules
- mosaic with bands, indexes -> RF classification -> spatial/temporal filters classification (specific planatations, automate manual rules) --> integration rules for land cover map (by biome, region) --> transition maps (all possibilities of comparisons)
- collection 1: 2008-2015, 2: 200-2016, 3 (by August): 1985-2017 (33 years)
- example map: http://mapbiomas.org --> can see statistics, filter by state, 5000+ municipalities (90% never had map), public slider interface, download data, see transitions matrix visualization
- Other apps: don't by soy in places that were forest before 2008 --> tool for compliance, table for transitions
- 21M ha of Net Loss of forest between 2000 and 2016
- accuracy (~70-80%) published with details, public can see major problems
- land use dynamics line graph, growth of cropland, see only biome going down
- other products: workspace GUI for GEE, scripts for GEE, methodological notes (ATBDs), web collect tools to collect samples, collection of samples for train/valid
- replication by partners, Chaco region and Amazon Basin
- collection 3 in August - project with Planet and Google to apply DL, TF to Planet imagery to classify objects, include time in classification

***Budhendra Bhaduri (BB), Corporate Research Fellow and Group Leader, Oak Ridge National Laboratory***
- ML, DL, and HPC
- LandScan: improving knowledge of pop dynamics
- last 20 years: people in pixels
- how to process large-scale sat img
- LandScan Global, USA (90m, trying to scale up to workd)
- 2006: High Res Pop Distrib and Dynamics (Big Data Fusion)
- foundational block in pop model to identify human-built structures
- extracting data product called settlement areas (8.5m res), building outlines, based on DCNNs, neighborhood mapping (similarities)
- data volume & needle in haystack: <3% land mass has human structure, enormous amount of img, nontrivial
  - USA: 9 trillion pix vs. 61 bil pix
- US: high res building map, on NAIP, 20k im, 10T pixels, 6TB compressed, GPUs only solutions. comprehensive data, first ever buildings database, backbone for FEMA hurricane/volcano response (produced last week, FEMA marks buildings)
  - BE QA/QC: mobile homes
- NAIP 1m vs.m <1m WV
- ML challenges: data shifts, clouds --> monitoring framework, things fall apart
  - sun angle, seasonality, sensor types, many practical challenges
  - same alg, vastly different results
  - ML as good as nature, snesors
- End-to-end obj detect/map (loc, geom)
  - scale DCNNs for super-pixel mapping, semseg
- Leveraging HPC and deep learning: in 2006, estimate of 30 years
  - CA HOG feature in less than 5 minutes on 1m res, 4 TM uncompressed
  - retrain, tweak for different simulations
- DL computing speed up
  - days to hours
  - settlement maps: 4 weeks to 7 days from 21 Tesla to 21 Volta
  - buildings: 3 days to 2 hours from 21 Volta to Titan 4708 Titan (Yemen in 1hr40m)
  - Summit: every node has 8 GPUs vs. Titan 1, cannot put data fast enough, staging data is real problem for throughput (2 hours to fraction of a minute)
- accelerated mapping of infra from pixels
  - mobile home park detection: interesting ML, vary by state by big in Florida, hard to find in FLorida
- imbalanced data issues: everything likes like MH, like railways
- also found swimming pools with NAIP, maintained vs. not
- hard to come up with training data
  - solar panels in SF
- settlemennt patters are socioeconomic indicators
  - neighborhood mapping, inferreing, DAmascus
- Settlement formality: edge orinetation distribution
- Lebanon: urban type criteria, CV challenge is birds eye view vs. human street view
- Karachi, Pakistan: formal vs. informal
  - challenge becomes source/perspective of crowdsourcing data (local? only partial capture notion)
  - slight road construction, but in our mind, road or water divides neighborhoods, and homes split

***Mark Friedl (MF), Professor, Boston University; and Co-Founder, Tellus Labs***
- New funding from NASA MEaSUREs to do global land cover map using LandSat (call for collaboration)
- Three Paradimgs for Mapping Land Cover:
  - Traditional ML
  - Semi-Supervised
  - Contiguous
- MODIS Land Cover Product: 
  - Global, 500 m, Annual
  - Best part is collections: Hierarchical classification schemet
- Training data: Never, enough, hard to maintain, quality hard, time consuming
  - 3k Modis
- Input Features: multi-temporal, multi-spectral (daily, 7 bands)
  - dimensionality reduction: 2500 raw features -> 50
- Alg
  - pre-processing
  - feature extraction
  - classification
- RF (ML not that hard to do)
- class conditional likelihoods combined with ancillary info (agri intesity, climate, elevation) for local context, tease apart large classes
- 80% well, 20% wrong/yr
  - post-processing
- bayes rule + priors
- HMM: 80% well, 20% wrong/yr, temporal correlation
- Serial Maps: Real Change vs. Classification Noise
  - savannas (woodlannd) vs. grassland: low density trees hard, labels flipping
  - 500m hard, MM approach to clean
- ABoVE
  - timeseries, annual since 1980s, Arctic
  - data-driven: what classes can classifier identify?
  - 10k loc, high-res: assign attributes, RF clustering: 15, define classes by clustered attributes
- Landscapes are dynamic: Logging in BC, Fire in Alberta
  - Recovery (Tasso)
- MEaSUREs: Moderate Spatial Resolution Data Record of 21st Century Global LC, LU, LCC
  - annual, from Landsat
- Continuous Change Detection & Classification (CCDC)
  - Fourier series at pixel, segments of stability, classify those, change point detection
  - looking for collab
- Thoughts on Taxonomy
  - hierarchical desirable
  - simpler schema, well-designed classes (e.g. forest, mixture classes real, multimodal)
  - LC != LU
  - agri large
  - change important characteristic
  - traditional ML not solution (features)
  - temporal info
  - ML sensitive to traiinng
  - best features req help
  - high quality training data hard
  - img interp non-triviail
  - local guidance
  - disturbance plan
  - easy to make bad maps
  - accuracy assessment essential (overall, per-class)

***Matthew C. Hansen, Professor, University of Maryland***
- nice change in granularity, liberating Landsat, see forest loss: 360 --> 1m pix
- Landsat
  - 250k img/year
  - 15pb online
  - high IO optimized (see BB), not sustainable
- importance of data & features > alg
  - preprocess by theme: water vs. forest vs. soybean
  - GFW product, forest change
- hierarchy: land vs. water, continuous % at the top, from cover to harder-to-observe use
  - sample for smaller themes
  - ancillary data for specific, satellite for targeting
  - change factors: how forests change
  - subtle long-term change (net tree cover gain, USSR reforestation ofsets Amazon deforestation) requires many observations
  - change class (e.g. tree cover loss), see logging roads & extractions, ephemeral signals
  - feature spaces tailored to theme of interest (multi-temporal metrics)
  - small-holder fields: mosaic, not per-pixel
- biggest challenge: maps targeting, but lots of time for sample based reference data for area estimation
  - samples provide area estimates > map estimate
  - e.g. forest cover change CAR: loss, buffer, none
  - timeseries, template reference, map --> pie charts of loss (from samples), land use outcomes
  - Target DRC forest clearing (pop growth)
- (Re BB): bare ground gain, even more of a needle --> sample based
- Big data = time-series
  - how to manage, pre-process?
- always reference data collection


***Chris Holmes (CH), Product Manager, Planet; and Technical Fellow, Radiant.Earth ***
- training data for ML
- geospatial background, how to build core accessible infra from  EO for ML
  - open ML frameworks and models, but unreasonable effectiveness of data (Google has 300x ImageNet)
  - "training data is the new new oil' e.g. plane detector
- Cloud Native Geospatial: workflows if geospatial started today
- PM for Cloud optimized GeoTIFF (from gdal)
  - stream data rather than make copies to take action
  - e.g. http://www.cogeo.org/map/
  - http://tiles.rdnt.io/ - raw pixels
   - Google Earth Engine: want to do input, not just output (like RF)
   - QGIS
  - no tile server, JS https://geotiffjs.github.io/cog-explorer/
  - RF: stream image in, formula for NDVI, model builder, analysis on-the-fly (one storage location)
- STAC (from Open Imagery Network, OSM for img)
  - OpenAerialMap: https://openaerialmap.org/
  - sat provider browser interfaces, similar but slightly different APIs
  - idea: Google > Portals
  - imagery avaialbe on website, to download & stream
  - approach: implementations/working code start, specific minimum core and leave open for evolution, extensions, open & community
- STAC + COG Infra
  - radically simpler data portals
  - data on cloud, accessible, can skip portal building
  - next phase
   - Cross Provider Analysis Ready Data, August workshop: pixel alignment, unusable data masks/clouds, atmospheric correction, image tiling
   - Open Labels: Open Labeled Training Data (DeepGlobe, ISPRS, SpaceNet...), geodiversity & global sampling
- Standards
  - format, ARD, image chip size, geo-diversity, label format, init classes
  - how can people fit own ontologies?



11:00 Lightning Talks 
                                        
Speakers (5 min + 2 min Q&A each):
Lyndon Estes (LE), Assistant Professor, Clark University
Christopher Lynnes (CL), EOSDIS System Architect, NASA
Murali Krishna Gumma (MKG), Remote Sensing and GIS Scientist, CGAIR
Ryan Engstorm (RE), Professor, The George Washington University 
Aislinn Pearson (AP), Head of Product Development, Innovative Solutions for Decision Agriculture
Drew Bollinger (DB), Developer, Development Seed/Synergise
James Gill (JG), Data Scientist, Facebook 
Markus Walsh (MW), Senior Research Scientist, Selian Agricultural Research Institute 
Rob Emanuele (RE), VP of Research, Azavea
David Grason (DG), Senior Manager, Platform Analytics, DigitalGlobe
David Lindenbaum (DL), Principal Engineer, CosmiQ Works

LE: Integrating HUmans and Machines to Map Smallholder-Domianted Agricultural Frontiers
•	problem: cropland maps inaccurate
•	approach: active learning, human label -> train & predict (ranked by uncertainty) -> new training samples from most uncertain -> human labels...
•	human component: crowdsourcing platform (Agircultural Mapping Platform)
•	accuracy assessment & consensus labelling (vs. reference maps), consensus labels (bayesian model averaging)
•	Machine component: featuer selection (CV), ML classifier (RF)
•	WorldView-2 accuracy >0.9 AUC, generalizable
•	key lesson: active learning more efficient, higher accuracy (faster convergence), much fewer training sites
•	current: Omidyar-funded, operationalize & improve AL, segment maps, demonstrate over Ghana
o	actiev learning optimized training sample for MASKRCNN

CL: Cloud Annalytics in NASA's Earth Science Data System
•	context: program for science research, more into apps with largest repo of multivariate heterogenous data
•	EOSDIS: data & info system, stores and distributes
•	projected data volumes: 200 PBs in 2020 from SAR...
•	Distribution increases similarity to cumulative volume
•	Solution: data-proximal analysis
•	Open Pipeline enables integration with exploitation platforms (Cumulus Data Archive ... --> ... Analytics Optimized Data Store value chainn, XaaS)
•	NASA Workshop (Feb 18): Enabling analytics in the cloud for earth science data
o	wide DL against NASA
•	Challenge: lack of sufficient training data

MKG: Geospatial activities & ICRISAT
•	5 major products: LUC, crop land changes in S. Asia, Africa, legth of growing periods, crop intensity (S. Asia)
•	ML: GEE, Sentinel & Landsat. 30m croplands product
•	GEE public data catalog
•	irrigated vs. rainfed cropland @ 30m in S. Asia
•	Challenges: limited ground data
•	Semi-automated techniques: (SMTs) spectral signatures --> mapping cropland areas, with automated decision trees
•	Spatial distribution of croplannds: last 5 years, 27 classses
•	Spatial distribution of rice & wheat, major dryland crops (13-14)

RE: Using High Spatial Resolution Satellite Imagery for Estimating Economica Well-being and Population in Sri Lanka
•	Motivation: what does poverty/population look like in imagery? WB wannts more accurate products
•	predict poverty, estimate pop
•	Sri Lankan Data: 2012 census, 10k people, to mask & household income survey
•	Imagery Data: purchased high res DG, 0.5m, 3500 sq km, $50k
•	Orbital Insight: DCNN, LandInfo: seg, GW: spatial & textural features
•	Modelling: >300 variables, poverty: avg log of consumption & # ppl at 10% poverty, Pop density
•	Regression (Lasso) with economists & RFs as a check
•	Post-Lasso Model Estimates: down to 27 variables, linear OLS model
•	poverty r-squared 0.6 pretty good, avg log of consumption similar
•	Scaling up census from survey: take survey and sample and predict out?
o	tree cover, elevation, built up (FB, other free data)
o	Poisson, Lasso, RF
•	Accuracy of predictions of GN pop density using Survey Data and Imagery Derived Features: 0.8 density, 0.6 pop
•	Challenge: how to operationalize, scale?
•	Q: what RS features predictive? A: spatial (building structures), building count, roads, road width. NDVI high in cities & wealthy, low else.
•	Q: undercounts with official gov't stats (Tamil minority)? A: not in this work, but seen undercount in other work. huge change in poverty rate.

AP: ISDA Data Scale Impact
•	startup with Gates Foundation funding
•	AfSIS
o	Phase I. Digital Soil Property Maps of Africa
o	Phase II: National for Ghana, Ethiopia, Kenya, Tanzania.
•	Workflow: RS covariates, legacy data rescue & new soil spectral diagnostics ($2.15 vs. $80-120/sample)
•	soil property maps hosted by ESRI, into Radiant
•	Challenge: get user communities of university graduates to add data
•	Challenge: want to know which crops & where, yield, mgmt interventions
•	Question: What do data standards need to look like? >20k in-field soil samples relatively standardized, across locations. moving into land use/crop type.
•	Goal: decision platform, with natl/ref/commer labs, & govts
•	Challenge: financial stability, data sharing, public goods (cost for revenue generation)
•	collecting validation data expensive, business model to pay back costs?
•	Q: Afr Reg Data Cube? A: yes

DB: ML at DevSeed
•	Projects:
o	road detection with world bank, SegNet called SkyNet, open infra, pulling labels from OSM
o	approach for human assisted mapping: WB, Pakistan/Nigeria/Zambia DNN for electricity infra (80-85% acc, small data), used by mapping
o	UrChn: OSM density, own building detection models, diff for OSM completeness
o	DL based Hurriane Intensity Estimator: wind speed, with NASA, live pipeline based on Cumulus framework
o	LC project: WRI in Kenya, Uganda, Malawi, some of 2016 Sentinel-derived LC maps, also historical LC classification from older img, have humans validate for RF
•	Tools
o	building detection alg on google deeplab v3 architecture (powering UrChn), futuer OSM completeness
o	label-maker: training data from OSM
o	Challenge: western-centric training data for high-rez
o	human curation of labeled data sets: in-browser prediction map

JG (Facebook Infrastructure) Conneting the World with Spatial Computing
•	Infrastructure: Unequal Distribution. almost 50% unconnected to Internet, ~25% no electricity, access to priorities
•	Questions: where people? roads (OSM)? greatest needs?
•	people? population density
o	CNN on DG 50cm w pop datasets from seasons (CU), highest-res pop maps, released when possible through columbia
o	previous state of art: too coarse to be useful, census block, can't answer many questions. 30m grid for building footprints
o	shines at finding isolated buildings in rural areas
•	roads? critical, open street maps
o	less than 1/2 roads of google maps in OSM
o	DG & NN to find roads, w OSM, contribute back to edit, validate faster
o	SInce May 2017, many provices in South Thailand completed
o	small roads and alleywas missed by traditional
o	Gates, Red Cross, World Bank, UNICEF, CSIP, WFP
•	Q: country-by-country? A: yes, would like global, roads longer bc segmentation --> network is work
•	Q: when is imagery from? A: mosiac from DG
•	Q: buillding pop? A: Columbia CSIN [new Grid3 refinining census data], but some census not reliable

MW: Land cover/use classification with GeoSurvey & ML
•	info sparse, global models ok for crops, little land data for 30M sq km
•	System of Environmental-Economic Accounting (SEEA): standardize cropland assessments, monitoring
•	GeoSurvey: "croplands present"? to tag 100k locations across Africa, http://geosurvey.ged.ai, can run APIs on img, can specify survey
•	paddy rice easy to tag, requires paddy buns & infra. vegetation counts & cover estimates
•	last 4 months: 2018 survey campaign, Malawi, Ethiopia, Nigeria, Ghana. proportial sample frame, 500k locs
•	GeoSurvey: ensemble prediction workflow: http://github.com/mgwalsh/Cropland-Atlas, reference labels, vetted labels, gridded features, into model calibration & stacking (RF, GB, BART, regularized regression)
•	Results 2015. p(Croplands present?), fast for prior probabilties, 1M observations
•	Tanzania predictions 18 http://github.com/mgwalsh/Cropland-Atlas, "woddy cover in croplands" --> building mask (in croplands), for field teams

RE: Azavea
•	geospatial software in Azavea, B-Corp, advance state of art in geospatial tech, apply for civic, social env impact i.e. Radiant Earth and OS tools/libraries (GeoTrellis Spark, Raster-VIsion DL, Raster Foundry platform)
•	img agnostic, skin to own brand like Radiant.Earth platform, remote sensing indexing through visual workflows & change detection
•	Challenge: ML workflows, tooling for annotating obj detecting bboxes, but validatinng, understanding img scores, into info feeds
•	need to build training sets with annotation tooling that's iterative, discovery process of class variety
•	LC: Potsdam semseg, prototypes of model exploration i.e. FCN with elevation vs. label layers, into platform and OS http://potsdam.geotrellis.io discovers food trucks and rare cases, how to decide
•	sem seg is hardest thing to label, high quality data: do we need to start with semseg, or can we work on chip clasification/object detection?

DG: GLobal Land Cover Classification
•	GBDX at DG, run algs at scale
•	(Un)Supervised LULC, model catalog, automating supervised LULC
•	Supervised: high-rez, acc product, different supported sensors, train system on GDBX, draw polygons, iterate model creation/generation, product
•	Geoscape LULC categories: continent of Australia, stringent accuracy spec, team building
•	Unsupervised data hard, run at continental scale (Russia, China, Africa) https://gbdxdocs.digitalglobe.com/docs/automated-land-cover-classification-1
•	Model Catalog: store models, search models: regionality, seasonality, sensor, text
•	Automating supervised LULC: model per biome, per season; load to ModelCatalog; pull model at runtime by regionality, seasonality
•	Other stuff: same, for object detection of ships, planes, cars, roads

DL: Accelerating Geospatial ML
•	SpaceNet 2.5 years ago: larger CV community focused on RS, sat img
•	no public data. SpaceNet high rez imagery and labels.
•	Making Remote Sensing Analytics Accessible: data (every quarter, year), tools (geospatial into CV, projections into pixels, bands & format), code (internal benchmarks), competitions (cash prizes, code must be open sourced)
•	released data sets: 1TB of high rez, 8-band, 5 cities, ~0.5M building footprint, 8k km road labels, 3 competitions, 100k prizes, OS 13 algs. 42 TB downloaded, 180-200 unique users/week.
•	4 cities focus: Las Vegas, Paris, Shanghai, Khartoum http://spacenetchallenge.github.com
•	Providing open access to geospatial labeled trainning data: 200m x 200m GeoTiff chips, building footprint labels in GeoJson
•	road: 300m x 300m GeoTiff chips, large CV, small RS img size
•	upcoming: new data, off nadir analysis sept 2018, road winter 2018

