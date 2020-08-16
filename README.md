# Consumer-Electronics-MFA-model-Althaf-2020-JIE
Matlab code used to perform consumer electronics MFA in Althaf et al 2020 JIE Manuscript

The material flow model for electronics calculates product inflows and waste flows in product units, product mass as well as material flows based on yearly -sales, lifespan and product material composition data inputs.
The models take four .csv files as the input sheets. The model inputs are uploaded with the codes.  Input sheet (.csv files) with product details for the model is named ‘Model Input_Baseline_Product Details’, input sheet with product material profile is named ‘Model Input Product Material Composition’ and input sheet with component material composition data should be named ‘Model Input Component Material Composition’. The model also takes HH population data as input named as ‘Model Input HH Population’. Data dictionary for the input sheets for the models are given below. 

DATA DICTIONARY FOR INPUT SHEETS

Product_Details_Input
Input sheet with product details has 10 columns.
Column 1: ProductID = Assign a number to each product. (Increment the number by one, when each product is entered, the maximum number in Product ID column indicates the number of products to be analyzed.
Column 2: Product Name =Enter Product Type
Column 3: Year = Enter years starting when the product was first sold in United states to the latest year.
Column 4: Sales_units = Enter totals sales units in each year
Column 5: Mass_of_Inflow_kg = Enter average mass of the product sold in each year.
Column 6: HHStock_units = Enter household stock data if available. This is just a place holder. The current model do not use stock data.
Column 7: Average_Stock_Mass_kg = Enter average mass of products in stock. This is just a place holder. The current model do not use stock data.
Column 8: Category= Enter the product category.
Column 9: Category Key
Column 9: Minimum_Lifespan= Enter any whole number other than zero (default= 1)
Column 10: Maximum_Lifespan= Enter any whole number other than zero (default= 10)
Column 11: Weibull_Scale = Enter Weibull scale parameters for the product lifespan distribution
Column 12: Weibull_Shape = Enter Weibull shape parameters for the product lifespan distribution

Product_Material_Composition_Input

Input sheet with product material composition has 14 columns.

Column 1: ProductID = Assign a number to each product. (Increment the number by one, when each product is entered, the maximum number in Product ID column indicates the number of products to be analyzed.
Column 2: Product Name =Enter Product Type
Column 3: Year = Enter years starting when the product was first sold in United states to the latest year.
Column 4: Fe = Enter the ferrous metal composition in the product (kg/kg) in each year
Column 5: Al = Enter the aluminum composition in the product (kg/kg) in each year
Column 6: Cu= Enter the copper composition in the product (kg/kg) in each year
Column 7: Other_metals = Enter the miscellaneous metal composition in the product (kg/kg) in each year
Column 8: Plastics = Enter the plastic composition in the product (kg/kg) in each year
Column 9: PCB = Enter the printed circuit board composition in the product (kg/kg) in each year
Column 10: LCD_module_CCFL = Enter the display glass composition in LCD display products (kg/kg) in each year
Column 11: LCD_module_LED = Enter the display glass composition in LED display products (kg/kg) in each year
Column 12: CRT_Glass = Enter the CRT display glass composition in products (kg/kg) in each year
Column 13: Li_battery = Enter the battery composition in LCD display products (kg/kg) in each year
Column 14: Others = Enter other material composition in products (kg/kg) in each year

Component_Material_Composition_Input
Input sheet with specific  material composition in components has 7 columns
Column 1: Year = Enter the years for which specific material waste flows are to be calculated.
Column 2: Au_PCB = Enter average gold composition in printed circuit boards (kg/kg) in each year
Column 3: Pb_PCB = Enter average lead composition in printed circuit boards (kg/kg) in each year
Column 4: Pb_CRT = Enter average lead composition in cathode ray tube glass (kg/kg) in each year
Column 5: Hg_LCD = This is just a place holder, the current model uses mercury composition in LCDs coded in the model and do not take the data as input
Column 6: In_LED = Enter average indium composition in liquid crystal display glass (kg/kg) in each year
Column 7: In_LCD = Enter average indium composition in liquid crystal display glass (kg/kg) in each year
Column 8: Li_LIB = This is just a place holder, the current model does not calculate Li flows
Column 9: Co_LIB = Enter average cobalt composition in lithium ion batteries (kg/kg) in each year

MODEL OUTPUTS

The model calculates waste flows by multiplying annual sales by product lifespan probability. 
Lifespan Distribution: The lifespan probability of products is assumed to follow a Weibull distribution function, generated based on the parameters provided by the user. The probability for a given range of lifespan is generated using the MATLAB function for cumulative distribution function for Weibull given as P = cdf ('Weibull', X, a, b) where X is the range of lifespan (minimum to maximum lifespan of the product), the probability of which is to be calculated, a is the shape parameter and b is the scale parameter. The models take minimum, maximum and Weibull parameters to generate the distribution.
The model generates results in 10 different excel sheets with MFA results at product level, bulk materials and component level, and specific material level. All mass outputs are in kg. The output sheets are named based on the data it contains.

