<img src="https://imgur.com/3Ua9VYU.png" style="float: left; margin: 18px; height: 75px"> 

# **Ames Housing Price Prediction**
---
## Problem Statement
---
My goal is to create a model to predict the sale price of new homes on the market in Ames, Iowa. Utilizing their 2006 to 2010 housing sales dataset, I will be utilizing a regression model to determine the sale price of upcoming listings, utilizing the house's features. 

## Data Dictionary
---
|Feature|Type|Dataset|Description|
|---|---|---|---|
|Lot_Frontage|float|ah_train|Linear feet of street connected to property|
|Lot_Area|int|ah_train|Lot size in square feet| 
|Mas_Vnr_Area|float|ah_train|Masonry veneer area in square feet| 
|BsmtFin_SF_1|float|ah_train|Type 1 finished square feet| 
|BsmtFin_SF_2|float|ah_train|Type 2 finished square feet| 
|1st_Flr_SF|float|ah_train|First Floor square feet| 
|2nd_Flr_SF|float|ah_train|Second floor square feet| 
|Low_Qual_Fin_SF|float|ah_train| Low-quality finished square feet (all floors)| 
|Gr_Liv_Area|int|ah_train|Above grade (ground) living area square feet| 
|Garage_Area|float|ah_train|Size of garage in square feet| 
|Wood_Deck_SF|int|ah_train|Wood deck area in square feet| 
|Open_Porch_SF|int|ah_train|Open porch area in square feet| 
|Enclosed_Porch|int|ah_train|Enclosed porch area in square feet| 
|3Ssn_Porch|int|ah_train|Three season porch area in square feet| 
|Screen_Porch|int|ah_train|Screen porch area in square feet| 
|Pool_Area|int|ah_train|Pool area in square feet| 
|Misc_Val|int|ah_train|Value of miscellaneous feature| 
|Id|int|ah_train|Observation number| 
|Bsmt_Full_Bath|int|ah_train|Basement full bathrooms| 
|Bsmt_Half_Bath|int|ah_train|Basement half bathrooms| 
|Full_Bath|int|ah_train|Full bathrooms above grade| 
|Yr_Sold|int|ah_train|Year Sold (YYYY)| 
|Year_Remod/Add|int|ah_train|Remodel date (same as construction date if no remodeling or additions)| 
|Half_Bath|int|ah_train|Half baths above grade| 
|Bedroom_AbvGr|int|ah_train|Bedrooms above grade (does NOT include basement bedrooms)| 
|Kitchen_AbvGr|int|ah_train|Kitchens above grade| 
|Fireplaces|int|ah_train|Number of fireplaces| 
|Mo_Sold|int|ah_train|Month Sold (MM)| 
|Street|object|ah_train|Type of road access to property| 
|Land_Contour|object|ah_train|Flatness of the property| 
|Lot_Config|object|ah_train|Lot configuration| 
|Bldg_Type|object|ah_train|Type of dwelling| 
|House_Style|object|ah_train|Style of dwelling| 
|Roof_Style|object|ah_train|Type of roof| 
|Mas_Vnr_Type|object|ah_train|Masonry veneer type| 
|Central_Air|object|ah_train|Central air conditioning| 
|Overall_Qual|object|ah_train|Rates the overall material and finish of the house| 
|BsmtFin_Type_2|object|ah_train|Rating of basement finished area (if multiple types)| 
|Paved_Drive|object|ah_train|Paved driveway| 

## *Summary of Analysis*
---
## Data Filtering
---

Removing columns with over 30% of values as NaN
-columns removed: 'Pool_QC', 'Misc_Feature', 'Alley', 'Fence', 'Fireplace_Qu'

Removing columns with over .8 correlation with another
-columns removed: 'Garage_Yr_Blt','TotRms_AbvGrd','Garage_Cars','Year_Built'

## Processing Data
---

The data was pushed through a preprocessing pipeline for the missing values in addition to categorical values. The preprocessing tools used were SimpleImputer, OneHotEncoder, and ColumnTransformer.

## Conclusion
---
The resulting cross-validation score is about 80% while the intercept returns 16560077.145470496 and the coefficients returned were as follows:

|Variable|Coefficient Returns|
|---|---|
|Lot_Frontage|-32.53325956863318|
 |Lot_Area|0.4070786081686819|
 |Mas_Vnr_Area|28.118920086264254|
 |BsmtFin_SF_1|7.583509926328487|
 |BsmtFin_SF_2|0.925147625320939|
 |Bsmt_Unf_SF|-2.408987301786542|
 |Total_Bsmt_SF|6.099672734942203|
 |1st_Flr_SF|14.321210842209382|
 |2nd_Flr_SF|20.951164068659352|
 |Low_Qual_Fin_SF|-10.932687301523849|
 |Gr_Liv_Area|24.33968834682687|
 |Garage_Area|24.183712029693005|
 |Wood_Deck_SF|17.09176468623761|
 |Open_Porch_SF|3.3820317333902707|
 |Enclosed_Porch|-0.1097024176831809|
 |3Ssn_Porch|59.147162890641624|
 |Screen_Porch|73.61870814387063|
 |Pool_Area|-103.09889620748285|
 |Misc_Val|-11.557400666602831|
 |Id|-12.887537035295829|
 |Bsmt_Full_Bath|8695.364645525948|
 |Bsmt_Half_Bath|-1022.8563766365244|
 |Full_Bath|11144.421299767959|
 |Yr_Sold|-8680.959393669711|
 |Year_Remod/Add|423.8231060608281|
 |Half_Bath|7934.3189658037745|
 |Bedroom_AbvGr|226.49308915070603|
 |Kitchen_AbvGr|-10834.815241728948|
 |Fireplaces|5783.31141729223|
 |Mo_Sold|40.574243893321274|
 |Street|9020.950843795552|
 |Land_Contour|27680.635194643233|
 |Lot_Config|20842.01316719633|
 |Bldg_Type|11390.198477277207|
 |House_Style|7403.010739108706|
 |Roof_Style|-3169.983968355127|
 |Mas_Vnr_Type|-10530.95870107419|
 |Central_Air|1380.7547777168013|
 |Overall_Qual|-8464.739086576186|
 |BsmtFin_Type_2|-12983.964369120644|
 |Paved_Drive|-23737.14969977319|