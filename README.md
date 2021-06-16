## Trulia Web Scraper
Using the Python Libraries Splinter and BeautifulSoup, we scrape data from https://www.trulia.com/, a real estate listing website, to identify trends in Virginia's real estate market. 

### Data Extraction
Using a jupyter notebook, the web scraping app was created which visits a url of trulia's website. The app creates a local web browser which is controlled by the python app to navigate multiple pages of HTML. Data is extracted by ID tags in the HTML, converted from string to int in cases when warranted, and stored in a Pandas DataFrame. 

![Extract](https://user-images.githubusercontent.com/12026338/122141913-58411b00-ce1c-11eb-9fd5-7629ef761312.PNG)


### Data Transformation
Data transformation takes place as part of the extraction process to ensure data is of appropriate type to use in analysis. All numeric data is transformed from string to integer, and categorical data remains as a string. Commas are removed from pricing strings, which can then be converted to an integer. 

![Transform](https://user-images.githubusercontent.com/12026338/122141941-655e0a00-ce1c-11eb-92e7-f37ddb6c725d.PNG)


### Data Loading
Data is converted to a CSV file via Pandas, and loaded into a mongoDB database, which can then be access locally or remotely. With the addition of multiple CSV files over time to the database, a more clear story can be told about the real estate market in Virginia. In particular, the use of time series to measure the changes in house prices for different counties in the state.

![Mongo](https://user-images.githubusercontent.com/12026338/122141958-6b53eb00-ce1c-11eb-9e96-0df3c28ef33b.PNG)



### Data Analysis
Using our initial data scraped from trulia, we were able to reach some conclusions about the real estate market en masse. 

From our data set, prices appear to be centralized around $300,000.  
![g1](https://user-images.githubusercontent.com/12026338/122141964-6ee77200-ce1c-11eb-96e6-e5f51629d235.PNG)

Price per Square Foot was centralized around $200.  
![g2](https://user-images.githubusercontent.com/12026338/122141979-77d84380-ce1c-11eb-952c-20b71d742272.PNG)


PCA yielded unclear results, requiring more indicators and data points to make a clear distinction.   
![g3](https://user-images.githubusercontent.com/12026338/122141985-7c9cf780-ce1c-11eb-89e4-ba057e93a2b6.PNG)


