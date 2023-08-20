# Machine Learning project: Detection of intentional forest fires
Comparison of the performance of some Machine Learning models for the task of detecting intentional forest fires in the Iberian Peninsula

Spain has been characterized as having a great predisposition to experience strong fires, specially during the summer season (a fact experienced by most regions with a mediterranean climate). The impact of these fires extends beyond the obvious ecological catastrophe that they represent at a local level, local communities are aslo affected, provoking, in many ocassions, an irreparable damage to private and public property. At an economic level, forest fires have a great impact in some of the main sectors of these rural communities, extending the damage beyonde the geographic or ecological frame. 

***1.1 Data source***

As we mentioned before, fire infromation is derived by the official reports fulfilled by the competent authorities in matters of fire extinction (a description of the data can be found in the official filling instructions in the following [link](https://www.miteco.gob.es/es/biodiversidad/temas/incendios-forestales/instrucciones_parte_incendio_tcm30-512355.pdf)), the historical data is already available thanks to the effort of **[CIV10](https://civio.es/nosotros/)** through their proyect **[España en llamas](https://civio.es/espana-en-llamas/metodologia/)** in which a web application allows viewing and browsing unpublished data of all forest fires with an affected surface of more than one hectare occurred in Spain between 2001 and 2015 (more than 80,000 observations).

***1.2 Intended use***

The intention of the present work is the **generation of a binary classification model that can help to predict if the causes that produced a fire were accidental or intentional in the Iberian Peninsula territory**. In order to achieve this task, documentation from a diverse range of sources will be gradually added and/or combine (fire, climate data and geographic information), so data quality could be evaluated in different stages of the analysis and through different machine learning techniques and deep learning algorithms.

* The first step, and the one that involves the use of the data collected by **[CIV10](https://civio.es/nosotros/)** , will be the modeling of this information (before adding the rest of variables) in order to evaluate the sufficiency of the data provide by the official fire reports to achieve the task of predicting the cause of a fire. (A second phase will be performe in order to evaluate whether or not climate and geographic information should be added as variables into the model, considering a previous analysis of the effects of these atributes over our predicted variable through exploratory data analysis and, in case of addition, how this atributes may result in a better or worst performance of the models).


***1.3 Data description***

The dataset has 82,640 observations taken during the years 2001 and 2015 (last years with **complete** information available) and contains the following fields:

- **ID**: Fire identifier
- **superficie**: Affected surface
- **fecha**: Fire date (format yyyy-mm-dd)
- **lat**: 	Geographic latitude of fire origine (WGS84)
- **lng**: Geographic longitude of fire origine (WGS84)
- **latlng_explicit**: If fire coordinates have been used (1) if coordinates of the closest municipality has been used (0)
- **idcomunidad**: Autonomous community identifier. (range 1-18)
- **idprovincia**: Province identifier (range 1-51)
- **idmunicipio**: Municipality identifier (codes vary from 1 to 999 in a none consecutive order)
- **municipio**: Municipality name
- **causa**: Cause identifier, with the following subclasification:


|cause|Code|
|:---:|:-------------:|
|fire caused by lightning|1|
|accident or negligence|2|
|accident or negligence|3|
|intentional fire|4|
|unknown cause|5|
|reproduced fire|6|


- **causa_supuesta**: (1) for supposed causes (causes not totally sure or completly verify), in case of complete certainty none or nan value
- **causa_desc**: Identifier wit a more complex description of the causes.
- **muertos**: 	Number of dead people due to the fire.
- **heridos**: Number of harmed people due to the fire.
- **time_ctrl**: Time to control the fire (in minutes)
- **time_ext**: Time to completly extinguished the fire (in minutes)
- **personal**: Number of people involved in the firefighting activities.
- **medios**: Number of logistic and technique resources that have participated in the extinction of the fire
- **gastos**: expense
- **perdidas**: economic loss
