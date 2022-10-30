# Pickled-fish-ZW

"Data, analysis script and associated files for:"			
"Clark TD, Raby GD, Roche DG, Binning SA, Speers-Roesch B, Jutfelt F, Sundin J (2020) Ocean acidification does not impair the behaviour of coral reef fishes. Nature 577: 370-375."			
 			
"Data collected by TDC, GDR, DGR, SAB, BSR, FJ and JS. Please refer to the manuscript for data collection methods and statistical analyses. For questions or to notify the authors if any errors are identified in the data, please contact Tim Clark (t.clark@deakin.edu.au), Graham Raby (graham.d.raby@gmail.com), and/or Dominique Roche (dominique.roche@mail.mcgill.ca)."			
			
##################			
# Workflow			
##################

Before data analysis and interpretation, the required R packages should be installed and loaded, including those required in the meta-analysis. After that, all the required csv files are read to help the subsequent research.
File processing based on the read files, summary and merging, including removal of outliers.
Meta-analysis was conducted.
Firstly, lnRR effect size is calculated, and then to the data that controls for the sampling variance of lnRR is fitted by this model. According to these findings, uncertainty in the overall meta-analytic mean, Study on measures of heterogeneity in effect size estimates and forest plot.
Finally, the study of publication bias. funnel plot and fit a Multilevel Meta-Regression model were used to draw a time-lag plot. And establishing a formal meta-regression model with some moderators. There is another very important study of file-drawer biases. Finally, the specific analysis content of publication bias is obtained and compared with other articles.		
			
			
##################			
# DATA file structure			
##################			

The name of the repository is "Pickled-fish-ZW", and it is a public repository containing three folders and four documents in different formats.

A document called "README.  md" is a description of a project that usually contains a description of the content and precautions for use.  It is usually a plain text file.

The document named "Assignment2_Zichu Wei_u7457435. rmd" is a Rmarkdown format file, which combines R code with documents, images, etc., to facilitate data exploration and analysis.

			
### clark_paper_data.csv ###			
			
columnHeading		description	
-------------		-----------	
Study			Code for each individual study
Authors			Authors of each paper	
Year (online)		Year the final paper was made available online
Year (print)	                Year the final paper was included in a journal volume/issue
Title			Title of each paper
Journal			Journal the paper was published in
Pub year IF		The journal impact factor for the year the paper was published; obtained from InCites Journal Citation Reports
2017 IF			The journal impact factor for 2017 (i.e., most recent journal impact factor); obtained from InCites Journal Citation Reports
Average n                               Average sample size for the study; average of indiviudal sample sizes for the contol and experimental groups
Effect type                              The type of effect concluded by the study regarding the effect of OA on behaviour; strong, weak, or no effect (see Supplementary Methods for details)
Climate (FishBase)                  Climatic region for each species; obtained from FishBase
Env cue/stimulus                    Whether or not the experiment included a cue or stimulus in the experiment (olfactory, visual, auditory, or physical)
Cue/stimulus type                  The type of cue or stimulus used
Behavioural metric                 The specific measure of behaviour tested
Life stage                                Life stage of the fish tested
			
*** Data used to summary statistic in the manuscript			
			
			
			
### meta-data_ocean_meta.csv ###			
			
columnHeading		description	
-------------		-----------	
Study			Code for each individual study
Authors			Authors of each paper	
Year (online)		Year the final paper was made available online
Year (print)	                Year the final paper was included in a journal volume/issue
Title			Title of each paper
Journal			Journal the paper was published in
Pub year IF		The journal impact factor for the year the paper was published; obtained from InCites Journal Citation Reports
2017 IF			The journal impact factor for 2017 (i.e., most recent journal impact factor); obtained from InCites Journal Citation Reports
Average n                               Average sample size for the study; average of indiviudal sample sizes for the contol and experimental groups
Effect type                              The type of effect concluded by the study regarding the effect of OA on behaviour; strong, weak, or no effect (see Supplementary Methods for details)
Species                                   The species used in each individual experiment
Climate (FishBase)                  Climatic region for each species; obtained from FishBase
Env cue/stimulus                    Whether or not the experiment included a cue or stimulus in the experiment (olfactory, visual, auditory, or physical)
Cue/stimulus type                   The type of cue or stimulus used
Behavioural metric                  The specific measure of behaviour tested
Life stage                                 Life stage of the fish tested
ctrl.n                                        Sample size of the control group
ctrl.mean                                 Mean of the control group
ctrl.sd                                       The standard deviation of the control group, calculated from ctrl.vartype
oa.n                                          Sample size of the experimental group
oa.mean                                   Mean of the experimental group
oa.sd                                        The standard deviation of the experimental group, calculated from ctrl.vartype
			
*** Data used to summary statistic in the manuscript			
			
			
			
### OA_activitydat_20190302_BIOL3207.csv ###			
			
columnHeading		description	
-------------		-----------	
loc			Location, and year, where the data were collected.	
species			Species name: Acanthochromis = Acanthochromis; Ambon = Pomacentrus amboinensis; Chromis = Chromis atripectoralis; Humbug = Dascyllus aruanus; Lemon = Pomacentrus moluccensis
treatment		"Elevated CO2 [CO2] (850-1,050) or control [Control] (400 - 450) groups"
animal_id			Fish identity
SL			Standard length of the fish in mm
size			Size grouping of the fish, separated at 15 mm standard length into 'big' or 'small'
activity		Number of seconds the fish was active per minute, averaged across the duration of the trial
comment			Comment with notes on the origin of the data

*** Data used to summary statistic in the manuscript			
			
			
			
### AIMS 2015 lat data.csv ###			
			
columnHeading		description	
-------------		-----------	
Study			Code for each individual study
Authors			Authors of each paper	
Year (online)		Year the final paper was made available online
Year (print)	                Year the final paper was included in a journal volume/issue
Title			Title of each paper
Journal			Journal the paper was published in
Pub year IF		The journal impact factor for the year the paper was published; obtained from InCites Journal Citation Reports
2017 IF			The journal impact factor for 2017 (i.e., most recent journal impact factor); obtained from InCites Journal Citation Reports
Average n                               Average sample size for the study; average of indiviudal sample sizes for the contol and experimental groups
Effect type                              The type of effect concluded by the study regarding the effect of OA on behaviour; strong, weak, or no effect (see Supplementary Methods for details)
Species                                   The species used in each individual experiment
Climate (FishBase)                  Climatic region for each species; obtained from FishBase
Env cue/stimulus                    Whether or not the experiment included a cue or stimulus in the experiment (olfactory, visual, auditory, or physical)
Cue/stimulus type                   The type of cue or stimulus used
Behavioural metric                  The specific measure of behaviour tested
Life stage                                 Life stage of the fish tested
ctrl.n                                        Sample size of the control group
ctrl.mean                                 Mean of the control group
ctrl.var                                     Measured variance of the control group
ctrl.vartype                              The metric of variance used for the control group (standared deviation, standard error, 95% confidence interval, or inter-quartile range
ctrl.sd                                       The standard deviation of the control group, calculated from ctrl.vartype
oa.n                                          Sample size of the experimental group
oa.mean                                   Mean of the experimental group
oa.var                                       Measured variance of the experimental group
oa.vartype                               The metric of variance used for the experimental group (standared deviation, standard error, 95% confidence interval, or inter-quartile range
oa.sd                                        The standard deviation of the experimental group, calculated from ctrl.vartype
lnRR                                         Raw effect size (natural log transformed response ratio)
|lnRR|                                       Absolute effect size (natural log transformed response ratio)
Weighted mean |lnRR|            The mean effect size for each study computed as the average of |lnRR| measurements for a given study
Notes                                       General notes regarding the nature of the data; includes rationale for omissions and other alterations to the data
JS check                                   Data checked by Josefin Sundin; X = yes
JCC final check                         Data final checked by Jeff Clements; X = yes
Precise sample size description in text?
                                                 Whether or not the study adequately described sample sizes in the text of the paper
Sample size source                  How the sample size for each group in each study was derived

*** Data used to help understanding in the manuscript			
			
			
##################			
# meta-data			
##################			
			
Meta-data means "data about data". Although the "meta" prefix means "after" or "beyond", it is used to mean "about" in epistemology. Metadata is defined as the data providing information about one or more aspects of the data; it is used to summarize basic information about data that can make tracking and working with specific data easier.
Example in this analysis：

Study			Code for each individual study
Authors			Authors of each paper	
Year (online)		Year the final paper was made available online
Year (print)	                Year the final paper was included in a journal volume/issue
Title			Title of each paper
Journal			Journal the paper was published in
Pub year IF		The journal impact factor for the year the paper was published; obtained from InCites Journal Citation Reports
2017 IF			The journal impact factor for 2017 (i.e., most recent journal impact factor); obtained from InCites Journal Citation Reports
Average n                               Average sample size for the study; average of indiviudal sample sizes for the contol and experimental groups
Effect type                              The type of effect concluded by the study regarding the effect of OA on behaviour; strong, weak, or no effect (see Supplementary Methods for details)
Species                                   The species used in each individual experiment
Climate (FishBase)                  Climatic region for each species; obtained from FishBase
Env cue/stimulus                    Whether or not the experiment included a cue or stimulus in the experiment (olfactory, visual, auditory, or physical)
Cue/stimulus type                   The type of cue or stimulus used
Behavioural metric                  The specific measure of behaviour tested
Life stage                                 Life stage of the fish tested