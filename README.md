# foodpy
A meal-creation program to meet macro-nutrient goals for meals.

I am new at python/CS, much of the terminology below may be wrong, although conceptually what I'm saying I'm trying to do is correct.

Problem: fitness nutrition programs offer readily available macro-nutrient (protein, fats, and carbs- "PCF") goals for the day, or per-meal, based on fitness goals, activity level, etc. However, the process of actually creating meals (without paying for full meal plans) to meet those goals is an arduous guess-and-check process, often involving Excel and manual transmission of PCF values per food type into tables, totalling PCFs vs. goals, change food/change serving size, etc. I am creating this out of necessity after experiencing immense frustration with the above process. Also, I need to learn python better...

Idea: create a program, in python, that by pulling from a database of foods, i.e. ground beef/chicken breast/potatoes, which includes their individual PCF contents, create meals via an selection algorithm which meet PCF goals for user, roughly including 1 protein-heavy food, 1 carb-heavy food, 1 fat-heavy food, and 1 vegetable.

Execution:

1) Datasource to Database
I will pull from the USDA Food Composition Databse (https://ndb.nal.usda.gov/ndb/search/list), using its API. In the process I will learn about API requiests. I will format requests, or manually edit requests, to just include food name, PCF content. 

Endstate (1): Pull at least 5 food types per P/C/F, i.e. P: lamb, ground beef, ground turkey, chicken, ribeye, C: potatoes, sweet potatoes, etc....

2) Database
I think this will require an SQL database. I will create three databases (P, C, and F), and start pulling in foods into the three databases. Possibly I can automate this from the API to sort into these three databases. More to follow... 

Endstate (2): 3 databases, each holding 5 food options per macro. 

3) Pulling from Database:
I will figure out how to use python to pull from the database(s), based on selection criteria

Endstate (3): I can pull data at request from a database(s), using python

4) Meal-plan Algorithm
Given a PCF/goal per-meal (parameters?), I will make, or research and select a pre-existing algorithm that fits my needs, an algorithm that pulls from the database(s), to create a 3-part meal composed of a protein-heavy food, fat-heavy food, and carb-heavy food. There are a lot of ways to approach this it seems, some ideas up front:

-A) Prefer one-macro, i.e. choose 1 protein, adjust C/F until meets Macro goals +/- 1 gram, if fails after X-attempts, choose new protein

-B) Cycle through macros, i.e. choose protein, try C/F, fail, choose carb, try P/F, etc.

-C) Do both above options, with set (commonly acceptable) serving sizes +/- 10%, i.e. one wouldn't want to eat 500 ounces of steak. Adjust serving size of primary x- times, try option A or B again.

-D) etc.

Endstate: a meal consisting of 1 protein-heavy, 1 carb-heavy, and 1 fat-heavy food option is generated, within tolerance of PCF goals for that meal

5) Output of Algorithm
After the meal-plan algorithm creates an output, figure out best way to output it. Likely this will be in the terminal, however would like to develop this further. 

Endstate: a way to see the algorithm's output



Future options:
-Create a GUI?
->Figure out how algorithm and GUI interact: backend to frontend
-Output MPA (meal-plan algorithm) into an excel table?
-Food prefernces? Rank fav. proteins, make vegetarian 
-Expand database
-....

Exciting times! 




