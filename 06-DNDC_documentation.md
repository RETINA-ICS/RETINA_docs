---
title: DNDC Documentation
---
# The DNDC Model

This portion of the documentation that started as RETINA specific, but will now be used more generally for anyone in the group using DNDC. 

The goal is to document all the ways that DNDC is being used across the group, and create a repository of code and documentation for each version of the model that is being used. 

For now the documentation centers around the version of DNDC that has been integrated in to PEcAn, which I am calling DNDC_M or DNDC "Matthias," the most recently developed version of the sourcecode for N-DNDC. 

## Versions of DNDC

Currently the RETINA group is working with the following versions of DNDC


1) **Agro-ecosystems**: Crop yield, soil carbon sequestration, nitrogen leaching, and trace gas emissions
   - The DNDC Model (Version 9.5) with PC User interface 
     - Interface: YES
     - Model with interface: http://www.dndc.sr.unh.edu/model/DNDC95.zip
     - Documentation: http://www.dndc.sr.unh.edu/model/GuideDNDC95.pdf
     - Scientific Documentation: pdf provided by Ed (where is it online?)
     - Source code available on one drive
   - Matthias Source Code - contians 3 versions 
      - DNDC "Idenways" which is the "original"
        - Interface: NO (running on docker)
        - Documentation: README files included with the source code written by Matthias
        - Source code available on one drive
      - DNDC "Matthias" <-- CURRENT VERSION USED BY RETINA
        - Interface: NO (running on docker)
        - Documentation: README files included with the source code written by Matthias
        - Source code available on one drive
      - Working version which is a mix of the two 
 - Potentially another "2014" version (need to check if/how this differs)
	  - Iden version before Matthias worked on it
	  - Version of DNDC may work best with Manure
	  - DNDC_source_Feb 17 2014
	  - Version shared by Jagadeesh for the project that Ed is on
  - Is there another version that was found on github
	  - The github version is what Umut is trying to get working with the manure flag...?
	  - [leaf-models-public/DNDC at master · praxik/leaf-models-public (github.com)](https://github.com/praxik/leaf-models-public/tree/master/DNDC)
	  
1) **Livestock Farms**: Greenhouse gas and ammonia emissions 
   - The Manure-DNDC Model 
     - Interface: YES
     - Model: http://www.dndc.sr.unh.edu/model/ManureDNDC.rar

2) **Forested Ecosystems**: Forest production, soil carbon sequestration, and trace gas emissions 
   - The Forest-DNDC Model 
     - Interface: YES
     - Model: http://www.dndc.sr.unh.edu/model/ForestDNDC.zip
     - Documentation: http://www.dndc.sr.unh.edu/model/ForestUserGuide.pdf

UPDATE on getting exe models running on the HPC (2-20-2024):
- It is going to be very difficult to get an exe to run on docker on the retina VM, maybe with wine
- We are going to reach out to the individual developers to ask if they have compiled command line versions, we could even give them examples of how we did it
- We could also possibly discuss moving away from docker altogether
## Github

https://github.com/RETINA-ICS

The idea is to put as many versions of DNDC on to the github as possible (as private repos) 
with documentation
and then do comparisons 


(Where Betsy got code from Matthias)
https://github.com/MatthiasMimault/DNDC_CC 

## DNDC Parameters

Note the documentation for DNDC is written from the perspective of using DNDC95 and DNDC_Matthias. However, even if the other versions of DNDC do not look exactly the same, the approaches to using them should be similar. 

### The DNDC interface 
(Difficutly: Easy)

The simplest way to choose the parameters for the DNDC model is to use the interface for DNDC. After choosing one's land type, soil type and crop type, most essential parameters will be populated with presets and it will be possible to do a preliminary run to see if the model is working. For information on using the interface to DNDC95, look at the documentation on DNDC95. 

### Library Parameter Files 
(Difficutly: Moderate)

Reading in default parameters from lookup tables based on crop id and soil type
#### Crop Params

#### Soil Params

#### ? Params


### The DNDC Source file 
(Difficutly: Advanced)






## The dnd file




### Role of the file

### How to create a dnd file

#### With the DNDC interface

#### By hand 

#### Using PEcAn and the RETINA app

---------------


##### Pre-made dnd files for the RETINA Project

###### Balruddery: Conventional Treatment
###### Balruddery: Sustainable Treatment

###### Glensaugh