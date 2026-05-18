Towards Climate-Smart Rewilding: An Integrated Framework for Biodiversity, Climate Change, and Society

To illustrate how the climate-smart rewilding framework can be applied, we conducted three spatially explicit analyses integrating ecological, climatic, and socio-economic dimensions. 

The basic idea of each analysis is to identify where there are opportunities for rewilding interventions to improve biodiversity and to assess their outcomes in one of the three components of the framework: climate mitigation, climate adaptation, or socio-economic benefits and risks. Each example focuses on a specific rewilding intervention, a particular biodiversity dimension affected by that intervention, and its outcome on one of the three components of the framework.

For each analysis, we first quantified and mapped the rewilding outcome, representing the spatial distribution of the targeted benefit or risk. We then delineated potential rewilding areas across Europe, identifying locations where the focal intervention (e.g., farmland abandonment or species range expansion) is most probable. Finally, we incorporated the biodiversity component by overlaying regions with high values of the relevant ecological attribute (e.g., ecosystem function, structure, or community composition) to indicate areas of existing ecological significance. 

These spatial analyses are not formal optimization exercises and sometimes rely on coarse proxies for the metrics used to represent the three components; however, they are intended to be illustrative of the framework’s potential to reveal synergies and trade-offs among biodiversity, climate, and socio-economic objectives 

These data and code allow to reproduce the figures 3 and 4 of the article, and figures of the supplementary materials. For more details on methods please refer to the .Rmd and to the supplementary materials. 


Data can be downloaded from [zenodo](10.5281/zenodo.20265711)
When downloading, create a folder called "data" with two subfolders "raw" and "intermediate". Put all the data in "raw".

1) Climate change mitigation


1.1 Current

Areas of low intensity of human use were selected as areas considered natural especially regarding their disturbance regime.
We used data C. Plutzar, C. Kroisleitner, H. Haberl, T. Fetzel, C. Bulgheroni, T. Beringer, P. Hostert, T. Kastner, T. Kuemmerle, C. Lauk, C. Levers, M. Lindner, D. Moser, D. Müller, M. Niedertscheider, M. L. Paracchini, S. Schaphoff, P. H. Verburg, P. J. Verkerk, and K.-H. Erb, "Changes in the spatial patterns of human appropriation of net primary production (HANPP) in Europe 1990-2006," Regional Environmental Change, vol. 16, no. 5, pp. 1225-1238, 2016. (https://boku.ac.at/wiso/isec/data-download) Those data were adapted to fill the entire area (original dataset limited to the EU). We chose those data for their regional precision. 

For updated data please look at Matej, S., Weidinger, F., Kaufmann, L., Roux, N., Gingrich, S., Haberl, H., ... & Erb, K. H. (2025). A global land-use data cube 1992–2020 based on the Human Appropriation of Net Primary Production. Scientific Data, 12(1), 511. and download at https://www.nature.com/articles/s41597-025-04788-1 


1.2 Potential 

Agricultural abandonment. 
We used data from Ceaușu, S., Hofmann, M., Navarro, L. M., Carver, S., Verburg, P. H., & Pereira, H. M. (2015). Mapping opportunities and challenges for rewilding in Europe. Conservation Biology, 29(4), 1017-1027. They employed the Dyna-CLUE land-use change model at a 1 km resolution (Verburg, P. H., & Overmars, K. P. (2009). Combining top-down and bottom-up dynamics in land use modeling: Exploring the future of abandoned farmlands in Europe with the Dyna-CLUE model. Landscape Ecology, 24(9), 1167–1181. https://doi.org/10.1007/s10980-009-9355-7) under four socio-economic VOLANTE scenarios. These scenarios capture alternative trajectories of agricultural practices, urban expansion, and policy frameworks across Europe, allowing for the identification of areas most susceptible to farmland abandonment under divergent socio-economic and governance conditions.

The original data distinguishes 4 categories: 1 = one scenario of abandonment is happening, 2 = two scenarios of abandonment are happening, 3 = three scenarios of abandonment are happening, 4 = four scenarios of abandonment are happening. We decided to include all cases where at least one scenario was happening.


1.3 Output of rewilding

The output of rewilding in terms of climate change mitigation was evaluated using the potential and unrealised carbon storage in aboveground biomass, below ground biomass and soil organic carbon. We used data from Walker, W.S., S.R. Gorelik, S.C. Cook-Patton, A. Baccini, M.K. Farina, K.K. Solvik, P.W. Ellis, J. Sanderman, R.A. Houghton, S.M. Leavitt, C.R. Schwalm, and B.W. Griscom. 2022. The global potential for increased storage of carbon on land. Proceedings of the National Academy of Sciences.doi: 10.1073/pnas.2111312119

For the figure, we used the potential carbon storage. We also used the unrealised carbon storage to calculate how much carbon would be stored if all potential abandonment was realised.

For original and complete datasets please refer to https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/DSDDQK




2) Climate change adaptation


2.1 Current

To identify areas of high structural connectivity in Europe, we calculated the effective mesh size (meff), a metric that quantifies the probability that two randomly chosen points in a landscape are connected without encountering a movement barrier, expressed as an equivalent area (Jaeger, J. A. G. (2000). Landscape division, splitting index, and effective mesh size: New measures of landscape fragmentation. Landscape Ecology, (15), 115–130). Meff was computed using land cover and infrastructure data from the ESA (2023) and OpenStreetMap. Barriers to movement included water bodies (rivers, lakes), areas of permanent ice and snow, and human land uses such as built-up areas, linear infrastructure, and intensive agriculture. The meff metric was applied using a moving window (10x10km) approach across Europe to generate a continuous gradient of habitat connectivity. Resulting values, which initially range from 0 to 100, were normalized to a 0–1 scale, and areas with Meff ≥ 0.8 were classified as highly connected.

m_eff     =    (1/A_total)  ∑(i=1)^n(Ai^2)     =    1/A_total (A1^2 + A2^2 + ⋯ + Ai^2 + ⋯ + An^2)

where A_total is the total area of the landscape, n is the number of habitat patches, and Ai is the area of patch i. This formulation expresses the probability that two randomly chosen points within the landscape fall within the same patch, multiplied by the total area, thereby yielding an area-equivalent measure of connectivity. Larger values of meff indicate fewer or larger barriers and, consequently, a more connected landscape. 


2.2 Potential

Agricultural abandonment. Cf 1.2


2.3 Output

To visualize potential climate change adaptation benefits, we generate a climate velocity map. We estimated the rate and direction of temperature change across Europe following the approach described by Loarie, S. R., Duffy, P. B., Hamilton, H., Asner, G. P., Field, C. B., & Ackerly, D. D. (2009). The velocity of climate change. Nature, 462(7276), 1052–1055. https://doi.org/10.1038/nature08649
Climate data were obtained from WorldClim version 2.1 (Fick, S. E., & Hijmans, R. J. (2017). WorldClim 2: New 1‐km spatial resolution climate surfaces for global land areas. International Journal of Climatology, 37(12), 4302–4315. https://doi.org/10.1002/joc.5086), released in January 2020, and included both historical and future projections of the BIO1 bioclimatic variable (Annual Mean Temperature). Historical data were extracted at 30-arc-second resolution (approximately 1 km²) for the period 1970–2000, while future projections were derived from CMIP6 downscaled datasets for 2061–2080 using the CMCC-EMS2 global climate model under the SSP245 scenario, maintaining the same spatial resolution. The temporal temperature gradient was calculated by subtracting historical from future mean temperatures and dividing the result by the number of years between the two periods, yielding an annualized rate of change.






3) Social benefits and risks 


3.1 Current

Wild mammals distribution

We are using the wildlife maps from the Rewild Europe Report (Fernández, N., Torres, A., Wolf, F., Quintero, L., & Pereira, H. M. (2020). Boosting Ecological Restoration for a Wilder Europe. Halle-Wittenberg: German Centre for Integrative Biodiversity Research (iDiv) and Martin-Luther-Universität.) They include Alpine ibex, Brown bear, Chamois, Elk, European bison, European lynx, European wolf, Iberian ibex, Iberian lynx, Pyrenean chamois, Red deer, Reindeer, Roe deer, Wild boar, Wild goat. 
Those data are an older version of the data base "TO BE ADDED"

For benefits we included Brown bear, Elk, European bison, European wolf, European lynx, Iberian lynx, Iberian ibex, Alpine ibex.
For risks we included Brown bear, European wolf.


3.2 Potential

We estimated the potential increase of species distribution by calculating the probability that cells not containing a focus species will gain that species in the future. For each species the same steps were applied:
1) Occurrences are coded as 0 = species absent, 1 = species present and 9 = species maybe present. We are changing all the 9 into 0. 
2) The distance of every 0 to the closest 1 is determined.
3) Calculate probability of colonization (form K e^-xdistance) (when distance = 0 it means the species is already there so probability is also 0). Based on Canis lupus dispersal values we apply rather 1/exp((log(2)/60) distance) (as the cells of the mammals distribution are 10x10km the probability max is 0.89)
4) Optionally the probability can be summed.


3.3 Output

Benefits: ecotourism. 
It is approached by people's willingness-To-Travel (WTT) to see wildlife (see Giergiczny, M., Swenson, J. E., Zedrosser, A., & Selva, N. (2022). Large carnivores and naturalness affect forest recreational value. Scientific Reports, 12(1), 13692. https://doi.org/10.1038/s41598-022-17862-0.)
 WTT is distributed among people, we use this distribution to determine the relation between distance to a cell and the share of people in the surrounding cells that will travel. Use the complementary lognormal CDF function (1 - CDF) and the density of people in a convolution to determine the amount of people going to one cell.

Conflicts: livestock and carnivores overlap.
We overlay the livestock density (sheep, goat, cow in animal per 1km2) and potential carnivores distribution increase. 
Data are from Gilbert, M., Nicolas, G., Cinardi, G., Van Boeckel, T. P., Vanwambeke, S. O., Wint, G. R. W., & Robinson, T. P. (2018). Global distribution data for cattle, buffaloes, horses, sheep, goats, pigs, chickens and ducks in 2010. Scientific Data, 5(1), 180227. 
They can be found at
Cattle https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/GIVQ75
Sheep https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/BLWPZN
Goats https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/OCPH42 






4) General layers

Along those datasets layers of countries borders, some European borders (we did not extend to Russia, Belarus, Ukraine, and Moldova) and coastlines.  





Authors: Magali Weissgerber, Gavin Stark, Néstor Fernández, Laura C. Quintero-Uribe, Marek Giergiczny,  Nikolaj Rauff Poulsen, Nacho Villar, Bjorn Mols, Elisabeth S. Bakker, Angus Monro Smith, Georg Winkel, Diogo Alagador, José M. Rey-Benayas, Josep Maria Espelta, Miriam Selwyn, Lluís Brotons, Tatiana Kluvankova, Stanislava Brnkalakova, Judith Kloibhofer, Reinhard Prestele, Henrik G. Smith, Alba Lázaro-González, Robert Buitenwerf, Elena A. Pearce, Jens-Christian Svenning, Joana Santana, Pedro Beja, Francisco Moreira, Sven Wunder, Miroslav Svoboda, Vlado Vancura, Almut Arneth, Arndt Hampe, Henrique M. Pereira
