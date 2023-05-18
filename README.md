# Web-scraping-and-Data-Analysis
Module 11 Assignment 
### This assignment involved :
   -  Identifying HTMLelements on a page 
   -  Identify their id and class attributes
   -  Use this knowledge to extract information via both automated browsing with Splinter and HTML parsing with Beautiful Soup. 

### 2 Deliverables - jupyter notebooks
   - Deliverable 1: Scrape titles and preview text from Mars news articles.
   - Deliverable 2: Scrape and analyze Mars weather data, which exists in a table.
      

### Deliverable 1: Scrape titles and preview text from Mars news webpage

   - Use automated browsing to visit the Mars news website and inspect the page to identify which elements to scrape to get the news
   - https://static.bc-edx.com/data/web/mars_news/index.html  
   - Create a Beautiful Soup object and use it to extract text elements from the website. 
   - Test it out by selecting one news article with select_one() 
   - After analyzing the the text elements returned, attempting to exract all the text elements using find_all and class params.
   - Storing all the results:
      -  Extract the titles and preview text of the news articles from the subset of the soup element scraped above above. 
      -  Store the scraping results in Python data structures as follows:
      -  Store each title-and-preview pair in a Python dictionary,mars_articles_dict. And, give each dictionary two keys: title and preview.
      -  example: 
         -  {
               'title': "NASA's MAVEN Observes Martian Light Show Caused by Major Solar Storm", 
               'preview': "For the first time in its eight years orbiting Mars, NASA’s MAVEN mission 
                witnessed two different types of ultraviolet aurorae simultaneously, the result of solar storms that began on Aug. 27."
            }
         
   - Store all the dictionaries in a Python list,mars_articles_list.
   - For loop is used to loop through the text elements:
    ![image](https://github.com/BijoyetaK/Web-scraping-and-Data-Analysis/assets/126313924/8a7ab84f-57f4-423b-8d85-ea37cf2ed6a0)
 
   - Print the list in your notebook:
      ![image](https://github.com/BijoyetaK/Web-scraping-and-Data-Analysis/assets/126313924/9511b9a1-3b52-4187-a5ad-4554de342216)
      
   -  Quit browser session
     

### Deliverable 2: Scrape and Analyze Mars Weather Data

   - Visit the Website : Use automated browsing to visit the Mars Temperature Data Site. Inspect the page to identify which elements to scrape.
   - https://static.bc-edx.com/data/web/mars_facts/temperature.html
   - Inspect the page by using Chrome DevTools to discover whether the table contains usable classes.
         
   - Scrape the Table : Create a Beautiful Soup object and use it to scrape the data in the HTML table:
      ![image](https://github.com/BijoyetaK/Web-scraping-and-Data-Analysis/assets/126313924/c21f10f0-6c30-4045-b935-79a80bd16773)
   - Extract all rows of data:
      ![image](https://github.com/BijoyetaK/Web-scraping-and-Data-Analysis/assets/126313924/bdde8187-39af-4718-812e-0588e4c139ea)
      ![image](https://github.com/BijoyetaK/Web-scraping-and-Data-Analysis/assets/126313924/6f2f4bce-b0c0-4b9b-aa8c-09ac38ed06fe)
   - mars_table has header rows(<th></th>), and data rows(<td></td>) under <tr> and class data-row.
   
   - Store the Data: Assemble the scraped data into a Pandas DataFrame. The columns should have the same headings as the table on the website. 
   - Explanation of column headings: 
      ![image](https://github.com/BijoyetaK/Web-scraping-and-Data-Analysis/assets/126313924/ca90294d-532a-413e-b1cc-5a21094bcb44)

   - Looping through the scraped data to create a list of rows: 
      ![image](https://github.com/BijoyetaK/Web-scraping-and-Data-Analysis/assets/126313924/76c9dfdd-7629-4da0-afd5-0f905bd37432)
   
      row list looks like: 
      ![image](https://github.com/BijoyetaK/Web-scraping-and-Data-Analysis/assets/126313924/4a6d3166-1ad3-4a68-812e-84466733c828)

         
   - Create a Pandas DataFrame by using the list of rows and a list of the column names: 
      ![image](https://github.com/BijoyetaK/Web-scraping-and-Data-Analysis/assets/126313924/d2a995fd-a3a4-440d-955b-c53e4a63417e)

   - Prepare Data for Analysis: Examine the data types that are currently associated with each column. 
                                 Cast (or convert) the data to the appropriate datetime, int, or float data types.
             
   - Analysis questions: 
      -  How many months exist on Mars?
      -  How many Martian (and not Earth) days worth of data exist in the scraped dataset?
      -  What are the coldest and the warmest months on Mars (at the location of Curiosity)? To answer this question:
      -  Find the average the minimum daily temperature for all of the months.
      -  Plot the results as a bar chart.
      -  Which months have the lowest and the highest atmospheric pressure on Mars? 
            -  Find the average the daily atmospheric pressure of all the months.
            -  Plot the results as a bar chart.
            -  About how many terrestrial (Earth) days exist in a Martian year? 
               -  Consider how many days elapse on Earth in the time that Mars circles the Sun once.
               -  Visually estimate the result by plotting the daily minimum temperature.
   
### How many months are there on Mars? 
   -  ![image](https://github.com/BijoyetaK/Web-scraping-and-Data-Analysis/assets/126313924/51f78ece-02eb-4819-891e-c849c2338377)

   - Plot the average temperature by month:
      ![image](https://github.com/BijoyetaK/Web-scraping-and-Data-Analysis/assets/126313924/75e9e6c5-586c-448c-a025-cf8d029d9b2a)

   - Identifying the colest and hottest months in Curiosity's location: 
   
      ![image](https://github.com/BijoyetaK/Web-scraping-and-Data-Analysis/assets/126313924/67c20a80-53aa-4384-a696-b72b29c1a6ab)

      -  From the plot, month 3 and 4 are the coldest and 8 & 9th are the warmest months. 
   
### Identify the lowest and highest atmospheric pressure on Mars: 
   -  Calculate average pressure by Martian month. 
   -  Plot the average pressure by month.
   
   ![image](https://github.com/BijoyetaK/Web-scraping-and-Data-Analysis/assets/126313924/00fcc6ad-6b18-4b64-80ff-25c1d8830dd5)

   - From the plot above, months 6 and 5 have the lowest atmospheric pressure. Month 2nd and 9th have the highest atmospheric pressure.   

### How many terrestrial (earth) days are there in a Martian year?
   
   -  Considered how many days elapse on Earth in the time that Mars circles the Sun once. 
   -  Visually estimate the result by plotting the daily minimum temperature. 
   - Calculating the peak to peak distance in the scatter plot using scipy. 
      -  reference: https://stackoverflow.com/questions/48023982/pandas-finding-local-max-and-min
     
   ![image](https://github.com/BijoyetaK/Web-scraping-and-Data-Analysis/assets/126313924/5556d016-acd9-4e3a-9604-c69b4142de5d)
   
   - Analysis: 
      -  The outlier peaks or spikes are ignored calculation.There could be some other natural phenomenon which could lead to high temperature. 
         Considering the approx peak to peak distance,is roughly 1490-825, or 665 days. A year on Mars appears to be about 665 days from the plot. 
         Internet search confirms that a Mars year is equivalent to 687 earth days.

   
#### Saving the Dataframe to a CSV file - mars_facts.csv
   
#### Quit browser session.
     
     
                 
                 
     
  

