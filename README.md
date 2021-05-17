# Inventory Management: Using SQL and Jupyter Notebooks to Better Organize Liquor Inventory

A friend of mine runs a bar and has consistently struggled to manage his inventory and financial records. He asked me to help him better organize his inventory, which I have chosen to do using MySQL connector library in Jupyter notebooks. These programs are set up so my friend, whom is quite computer illiterate, can simply open the corresponding program for whichever task he would like to do (viewing inventory records, update menu items, calculate cost ratios, etc.), simply hit "Run progam" at the top, and can insert his records as see fit.

Programs are separated into two categories for easier use: ***'Search'*** files,  and ***'Update'*** files.

This repository does not contain all programs written for the bar, just a few to simply demonstrate the mechanics of the tools used.

All programs were written between July - September of 2020.

**NOTE:** All programs are written to use data and passwords stored on the bar's personal server. For this reason, these codes will not run on an external system.

## "Search" Records

The **'Search'*** folder contains programs which primarily focus on searching through available records by calling specific data from the **bar-invetory** database.

### Search Inventory Records

To search the bar's inventory of available liquors, provided are two programs, ****search_inventory.ipynb**** and ****search_inventory_num.ipynb***, both of which call data from the **inventory** table. To search for a dimension (string) field with a text specifyer (eg. liquor, brand, etc.), open the ****search_inventory.ipynb**** program, then first specify with "Select" what field to search, then the search term, "As". What returns is a pandas Dataframe of all information regarding that search used (this data will be discussed further under "Insert into Inventory"). 

In the example below, the user wishes to search the subliquor "Bordeaux" within the liquor category "Red Wine". To do this, he first specifies to select from the "subliquor" column, then specifies the search term, "Bordeaux". What returns is the only Bordeaux in the inventory, "Chateau Bellevue Bordeaux", with all associating data.

![map_chart](Images/Search_inventory_ss.png)

To search a numeric (interger or float) variable, open the ****search_inventory_num.ipynb**** program, then first specify with "Select" what field to search, then place the comparative qualifyer the search term, "To". In the following example, the user wishes to find what liquors have a price greater than $10. To do this, he specifies to search "Price", then states he wants ">" (greater than), and finally specifies "10". What returns is data from 75 products, all of which have a price greater than $10.

![map chart](Images/Search_num.png)

### Search Cocktail List

In order to search data regarding mixed drinks served and sold at the bar, the user will use the ****search_cocktail.ipynb**** program, which calls data from two sources, the **drinklist** table, which contains data regarding ingredients and amounts for specific drinks (this will be discussed further under "Insert into Cocktail List"), and the **drink_profit** view, which itself calls and runs calculations on data from the **Inventory**, **drinklist**, and **drink_menu**. The only specifier requested from the user is the name of the drink, and returned is the list of ingredients with amounts, the price, the cost to make, and the profit produced for one drink.

The **drink_profit** first pulls the cocktail name and price from the **drink_menu** table. It then calculates the cost of to produce one drink by calling the ingredients and amounts from **drinklist** and joins price and volume from **inventory** to calculte exact cost to produce one drink. It then joins to subtract Cost from Price to produce Profit. 

In the example below, the user searches for a simple cocktail, a Rum and Coke, with Bacardi Rum. Returned are the two ingredients, the menu price, cost, and profits produced on one order.

![map_chart](Images/Search_drinklist_ss.png)

## "Update" Records

The **'Update'*** folder contains programs which primarily focus on adding, changing, or otherwise updating the data stored in the **bar-invetory** database.

### Insert into Inventory

![map_chart](Images/Insert_into_inventory_ss.png)

### Insert into Cocktail List

![map_chart](Images/Insert_int_drinklist.png)

### Update Inventory Records

![map_chart](Images/Update_inventory_ss.png)

