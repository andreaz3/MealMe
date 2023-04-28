# Project Report: 
> Andrea Zhou, Lina Mei, Hanning Zhang, Kaitlyn Chan

## 1. Changes in Direction
> Please list out changes in the directions of your project if the final project is different from your original proposal (based on your stage 1 proposal submission).

Our original proposal included the feature for users to add and remove their own recipes, however we ended up not implementing this idea so we could focus on building out a full-functioning UI for the search page.  Our original proposal also included a recipe randomizer, which was intended to recommend  one random recipe to the user that deviated from the recipes they normally like, however we decided to scrap this idea and instead focus on optimizing our recommendations page. 

## 2. Usefulness
> Discuss what you think your application achieved or failed to achieve regarding its usefulness.

The application successfully offers recipe recommendations based on the user’s favorite recipes. This is useful for users who are looking for new and exciting recipes to try. Additionally, allowing users to search and filter recipes based on specific criteria such as number of steps or related tags can make it easier for users to search through recipes that suit their needs, saving time. Clicking on the recipes provides information about the time, ingredients and steps of the recipes. The relatively simple user interface keeps it straightforward and easy to navigate.

## 3. Changes in Schema
> Discuss if you changed the schema or source of the data for your application

For our schema, we initally set all VARCHAR columns to 50, however we realized we needed more space to store longer strings of text values into many of our database tables, so we increased VARCHAR from 50 to 200. In terms of our data, we did not change the source of the data for our application. It is still the Foods.com dataset from Kaggle that is described in our proposal. 

## 4. Changes in Implementation 
> Discuss what you change to your ER diagram and/or your table implementations. What are some differences between the original design and the final design? Why? What do you think is a more suitable design? 

We did not change our ER diagram, but we did have to expand some of the VARCHAR counts for our table implementations. Overall, the designs were the same, but we had to account for recipe titles and ingredient names that were longer than expected. This change was necessary for our queries to work, so yes, it was more suitable.

## 5. Changes in Functionalities
> Discuss what functionalities you added or removed. Why?

We kept our core functionalities which were the favorites page and the inventory page. The favorites page allows users to revisit their liked recipes and the inventory allows users to mark what they have in stock. We changed the random recipe generator which originally was meant to generate one recommended recipe to a recommendation page which suggests a list of over 10 recipes based on what they like and what they have in stock. We thought that it would be more beneficial for users to have a larger variety of recipes that captures both the types of recipes that they might like and  ingredients that they currently have in stock. A more specific functionality that we changed was that we mentioned an insert or delete to favorites or inventory should trigger an update to the recommendation relation. We removed this because a user could be adding multiple ingredients at a time, or change their mind about favoriting a recipe. It is not necessary to update their recommendations unless they are looking at it. Instead, the recommendations are generated when users check their recommendations page.


## 6. Advanced Database Program
> Explain how you think your advanced database programs complement your application.

Our advanced database programs complemented our application by providing an efficient way for user’s to interact and query the database. Our search query allows users to filter through all the recipes to find the ones that they want. For users on a time crunch, they can use the slider to find easy and fast recipes. Or for users with dietary restrictions, they can use the tags to find vegan or nut-free recipes. Our advanced query provides these recipes in a human-readable format. Our stored procedure utilizes multiple advanced queries to find recommended recipes for each user based on their favorites and inventory, making it even easier for users to try new recipes that they will like.


## 7. Technical Challenges
> Each team member should describe one technical challenge that the team encountered.  This should be sufficiently detailed such that another future team could use this as helpful advice if they were to start a similar project or where to maintain your project.

**Andrea**: One technical challenge we encountered was setting up the datatables. Our estimation for the VARCHAR count for recipe titles and ingredients were too low, which caused an inconsistency in our database when we tried to query. In addition, some of the files were really large, which results in corruption if we opened the file before uploading. We realized this later in the process, and had to modify the schema of the tables and reupload the data. <br>


**Lina**: One technical challenge we encountered was running the repository on our local machines. While we were able to pull the repository from github, some packages were still missing/uninstalled despite running npm commands in the terminal to install it. An example was the program not detecting npm concurrently or the react packages. This prevented us from being able to run the website on our local servers right away. <br>


**Hanning**:  One technical challenge we encountered was importing the data. When we first imported the Time attribute of the recipes, it showed a random long VARCHAR instead of INT.  It took quite a long time to fix it, before we could write and execute our queries. <br>


**Kaitlyn**:  One technical challenge we encountered while developing our application was connecting our GCP database instance to our express server. Although there were some tutorials/examples provided by the TAs, we had to try out different methods as the database wasn’t connecting properly to the app, and the final process to set it up ended up a little tedious (we had to download google-cloud-sdk, setup public keys, etc…). Replicating these steps to get everyone’s machines to connect also ended up a little tedious as each person encountered small issues, but we got it to work in the end. 


## 8. Any Other Changes
> Are there other things that changed comparing the final application with the original proposal?

Aside from some slight changes in direction regarding the recipe randomizer, allowing users to create and manage their own recipes,  and increasing the VARCHAR count (as mentioned in points 1 and 3 of this report), all other components and functionalities suggested in our original proposal translated over to our final application.

## 9. Future Development
> Describe future work that you think, other than the interface, that the application can improve on

The application could expand to allow users to add their own recipes to the Recipes page. Then, other users would have access to these recipes and favorite them if they like them. We had already started thinking ahead about this feature by implementing the new ingredients trigger. If future recipes include that ingredient, recommendations of that recipe and similar new recipes can be made via matching ingredients.


## 10. Division of Work
> Describe the final division of labor and how well you managed teamwork.

For the first 3 stages, we all worked together to write the documents, DDLS, queries, and upload the data to GCP. For stage 4, Kaitlyn was in charge of setting up the app and connecting it to GCP, Andrea was in charge of Inventory, Lina was in charge of the Login, Hanning was in charge of Search. We each wrote our own queries. For stage 5, Andrea implemented the trigger for the inventory, Lina built the favorites functionality, Hanning continued to work on the search, and Kaitlyn implemented the stored procedure and UI for the recommendations page and the user authentication. While the main tasks were split up, we helped each other where we could. For example, when Andrea was connecting the routes for the stored procedure, she noticed that Kaitlyn had worked on the search UI, which was similar to the recommendations UI. So while Andrea worked on the backend of that part, Kaitlyn worked on the frontend. Additionally, some of us lacked React experience, which others had more, so we learned from one another in that aspect as well. Overall, the teamwork was very positive and beneficial to our learning process.

