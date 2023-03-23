# NoSQL-Databases



Table of Contents
=================

  * [Background](#background)
  * [Objective](#objective)
  * [Method](#method)
  * [Part 1: Database and Jupyter Notebook Set Up News](#part-1-database-and-jupyter-notebook-set-up)
  * [Part 2: Update the Database](#part-2-update-the-database)
  * [Part 3: Exploratory Analysis](#part-3-exploratory-analysis)
  * [References](#references)
  
  
  
## Background
  

The UK Food Standards Agency evaluates various establishments across the United Kingdom and gives them a food hygiene rating. I have been contracted by the editors of a food magazine, *Eat Safe, Love,* to evaluate some of the ratings data in order to help the journalists and food critics decide where to focus future articles.
  
  

## Objective
  

There are two technical products with the submission of the following deliverables:

* **Deliverable 1:** A Jupyter notebook containing code that imports the data, sets up and updates the uk_food database.

* **Deliverable 2:** A Jupyter notebook containing code that performs the exploratory analysis queries in the database.



## Method
## Part 1: Database and Jupyter Notebook Set Up


Use NoSQL_setup_starter.ipynb for this section of the challenge.

    1. Import the data provided in the establishments.json file from Terminal.
    Name the database uk_food and the collection establishments. 
    Then import the data from Terminal to a markdown cell in the notebook is provided.
    
    2. Within the notebook, import the libraries needed: PyMongo and Pretty Print (pprint).
    
    3. Create an instance of the Mongo Client.
    
    4. Confirm that the database was created and loaded the data properly:
        * List the databases in MongoDB. Confirm that uk_food is listed.
        * List the collection(s) in the database to ensure that establishments is there.
        * Find and display one document in the establishments collection using find_one 
        and display with pprint.
        
    5. Assign the establishments collection to a variable to prepare the collection for use.



## Part 2: Update the Database


Use NoSQL_setup_starter.ipynb for this section of the challenge.

The magazine editors requested modifications for the database prior to performing any queries or analysis. The following changes were made to the establishments collection:

    1. Include an exciting new halal restaurant that just opened in Greenwich in the analysis. 

    2. Find the BusinessTypeID for "Restaurant/Cafe/Canteen".
    Return only the BusinessTypeID and BusinessType fields.

    3. Update the new restaurant with the BusinessTypeID found.

    4. The magazine is not interested in any establishments in Dover.
    The number of documents contained by the Dover Local Authority was checked and removed.
    The number of documents were re-checked to ensure they were deleted. 

    5. Use update_many to convert latitude and longitude to decimal numbers.
    


## Part 3: Exploratory Analysis


Eat Safe, Love have specific questions they want answered, which will help them find the locations they wish to visit and avoid.

Use the NoSQL_analysis_starter.ipynb for this section. Some notes to be aware of while you are exploring the dataset:

    * RatingValue refers to the overall rating decided by the Food Authority and ranges from 1-5. 
    The higher the value, the better the rating. 
    Note: This field also includes non-numeric values such as 'Pass', 
    where 'Pass' means the establishment passed inspection but is not given a number rating.
    
    * The scores for Hygiene, Structural, and ConfidenceInManagement work in reverse. 
    The higher the value, the worse the establishment is in these areas.


Use the following questions to explore the database, and find the answers, to provide to the magazine editors.

Unless otherwise stated, for each question:

* Use count_documents to display the number of documents contained in the result.
    
* Display the first document in the results using pprint.
    
* Convert the result to a Pandas DataFrame, print the number of rows in the DataFrame, and display the first 10 rows.


    1. Which establishments have a hygiene score equal to 20?
    
    2. Which establishments in London have a RatingValue greater than or equal to 4?
    
    3. What are the top 5 establishments with a RatingValue of '5', sorted by lowest hygiene score, 
    nearest to the new restaurant added, "Penang Flavours"? 
    
    4. How many establishments in each Local Authority area have a hygiene score of 0? 
    Sort the results from highest to lowest, and print out the top ten local authority areas.



## References


UK Food Standards Agency (2022). UK food hygiene rating data API. https://ratings.food.gov.uk/open-data/en-GB. Contains public sector information licensed under the Open Government Licence v3.0.
Accessed Sept 9, 2022 and Sept 12, 2022 with the establishment settings as follows: longitude=51.5072, latitude=-0.1276, maxdistancelimit=4567, pagesize=10000, sortoptionkey=distance, pagenumber=(1,2,3,4,5,6,7,8).

* Dataset provided by edX UofT Data Analytics, which had been generated by Trilogy Education Services, LLC. 

- - -
