# py-1c-different-bases-cost-alignment  
* The practical sense of the scipt is to make products between 2 databases to have the same cost  
 * 1'st database is used for operational accounting   
 * 2'nd database is used for accounting and taxes. It also has the correct accounting costs.  


The items where the names between 2 db's are different but have the same code will be displayed in different_names.xlsx
different_names.xlsx also contains items unique for BUH or UT file

The biggest problem - the remains table has additional column called "Серия"(series) - an item  
from the 1'st database has a quantity in the context of series  


The trick is to take the costs of the same items from 2'nd accounting database and ditribute them  
for the 1 database.  


The cost is taken from BUH.csv and distributed among the item series from the UT.csv  


Incoming data:  
* BUH.csv with fields:  
    * Номенклатура	str     - item name  
    * КодНоменклатуры str     - unique code of an item  
    * Склад	        str     - warehouse name  
    * Количество	    float   - quantity   
    * Сумма           float   - sum  
    
* UT.csv with fields:  
    * Номенклатура    str     - item name	  
    * КодНоменклатуры	str     - unique code of an item  
    * Склад	        str     - code of an item  
    * Количество	    float   - quantity   
    * Сумма	        float   - sum  
    * Серия	        str     - item series  
    * КодСерии        str     - code of item item series  
 
 
Outcoming data:  
* final_UT_BUH.xlsx    

