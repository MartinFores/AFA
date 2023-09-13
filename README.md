# AFA
The Alien Flora of Australia (AFA), a unified Australian national dataset on plant invasion
by Martín-Forés, I., Guerin, G.R., Lewis, D., Gallagher, R.V., Vilà, M., Catford, J.A., Pauchard, A. & Sparrow, B.

Biological invasions are a major threat to Australia. Information on alien flora in Australia is collated independently by different jurisdictions, which has led to inconsistencies at the national level, hampering efficient management. To harmonise different information sources, we present the Alien Flora of Australia (AFA), a nationally unified dataset. To create the AFA, we developed an R script that compares existing data sources (the Australian Plant Census and state and territory censuses), identifies mismatches among them and integrates the information into unified invasion statuses at the national scale. The AFA follows the taxonomy and nomenclature adopted for the Australian Plant Census, introduction status and impact of plants known to occur in Australia. The up-to-date information presented in this dataset can aid early warning of alien species invasions, facilitate decision-making at different levels, and biosecurity at national scale. The associated script is ready to be implemented into new versions of the AFA with updated releases of any of the data sources, streamlining future efforts to track of alien flora across Australia. Individuals who use these data for publication or this script may cite this data paper.

This contains the R script associated with the AFA. As such, it corresponds to the Supplementary material of the above mentioned data manuscript. 

This R script combines the Australian Plant Census (APC) with all the Australian state and main territory flora censuses in order to detect mismatches between species nomenclature and introduction status accross Australia. 
The script can be used with future releases of the APC or any of the state floras, to automatize this process in the future, as long as the format is the same for the source datasets. 
The script follows the APC taxonomy as the most recognised authority of taxonomic nomenclature for Australian flora, however it also incorporated standardised nomenclature from GBIF and WFO in order to adapt the tool to other international plant taxonomy sources. 
The introduction status recorded in the outcome is based on Blackburn et al. (2011) and the integration on invasion information across Australia conducted by Martín-Forés et al. (2023). Species are therefore classified in the AFA as native, native colonising or native potentially colonising (when they were also introduced or potentially introduced, respectively within the same state or territory of origin), introduced, naturalised (when forming self-sustaining populations) – we also stated whether, for the two former ones, the status was doubtfully or formerly when that was the case –, harmful invasive (when recorded as invasive causing negative impacts according to the Australian Globar Registry of Introduced and Invasive Species (GRIIS)), presumed extinct, or uncertain origin. 

################################

Before proceeding to use this script, there are a few prior steps that need to be taken:

1. Download plant censuses from states and main territories, or request them to pertinent authorities, and download the Australian Global Registry of Introduced and Invasive Species:
   
#Australian Plant Census (APC) = https://biodiversity.org.au/nsl/services/export/index


#State and main territories plant censuses

#Australian Capital Territory (ACT) = https://www.cpbr.gov.au/cpbr/ACT-census/vascular-gen-alpha.html

#New South Wales (NSW) = request to the Royal Botanic Gardens, as it cannot be directly downloaded from electronic sources

#Northern Territory (NT) = http://eflora.nt.gov.au/NTSpeciesList?heading=sNTSpecies

#Queensland (QLD) = https://www.data.qld.gov.au/dataset/census-of-the-queensland-flora-and-fungi-2022/resource/548d9394-c94c-4512-a2fa-8f667dac2a2f

#South Australia (SA) = https://data.environment.sa.gov.au/Content/Publications/vascular-plants-bdbsa-taxonomy.xlsx

#Tasmania (TAS) = https://flora.tmag.tas.gov.au/resources/census/

#Victoria (VIC) = https://vicflora.rbg.vic.gov.au/flora/download?q=*:*

#Western Australia (WA) = request to the Western Australian Herbarium, as it cannot be directly downloaded from electronic sources


#Australian Global Registry of Introduced and Invasive Species (GRIIS) = https://cloud.gbif.org/griis/resource?r=griis-australia&v=1.9#anchor-downloads

#Once downloaded them, save them as follows in your working directory:
#APC_original.csv
#plant_census_ACT.csv
#plant_census_NSW.csv
#plant_census_NT.csv
#plant_census_QLD.csv
#plant_census_SA.csv
#plant_census_TAS.csv
#plant_census_VIC.csv
#plant_census_WA.csv
#griis.csv (taxon file)
#invasive_griis.csv (speciesprofile file)
#distribution_griis.csv (distribution file)

#Download and save the associated R source file AAFSS_functions.R and AAFSS_secondary_functions.R to your working directory

