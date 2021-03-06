## Trulia Web Scraper
Using the Python Libraries Splinter and BeautifulSoup, data is scraped from https://www.trulia.com/, a real estate listing website, to identify trends in Virginia's real estate market. 

### Data Extraction
Using a jupyter notebook, a web scraping app is created which visits a url of trulia's website. The app creates a local web browser which is controlled by the python app to navigate multiple pages of HTML. Data is extracted by ID tags in the HTML, converted from string to int in cases when warranted, and stored in a Pandas DataFrame. 

![Extract](https://user-images.githubusercontent.com/12026338/122141913-58411b00-ce1c-11eb-9fd5-7629ef761312.PNG)


### Data Transformation
Data transformation takes place as part of the extraction process to ensure data is of appropriate type to use in analysis. All numeric data is transformed from string to integer, and categorical data remains as a string. Commas are removed from pricing strings, which can then be converted to an integer. 

![Transform](https://user-images.githubusercontent.com/12026338/122141941-655e0a00-ce1c-11eb-92e7-f37ddb6c725d.PNG)


### Data Loading
Data is converted to a CSV file via Pandas, and loaded into a mongoDB database, which can then be access locally or remotely. With the addition of multiple CSV files over time to the database, a more clear story can be told about the real estate market in Virginia. In particular, the use of time series to measure the changes in house prices for different counties in the state.

![mongo](https://user-images.githubusercontent.com/12026338/122306312-35733d00-ced6-11eb-81c2-334156505280.png)

Data is also added to a pymongo server in attached notebook, which could be accessed via a flask app and displayed on an html webpage. 

![pymongo](https://user-images.githubusercontent.com/12026338/122303263-47061600-ced1-11eb-9906-af1e879f7348.png)


### Data Analysis
Using our initial data scraped from trulia, we were able to reach some conclusions about the real estate market en masse. 

From our data set, prices appear to be centralized around $300,000.  

![g1](https://user-images.githubusercontent.com/12026338/122305937-a23a0780-ced5-11eb-8f28-ff09541fa0fc.png)


Price per Square Foot was centralized around $200.  

![g2](https://user-images.githubusercontent.com/12026338/122305999-bbdb4f00-ced5-11eb-92da-4abbba88a7e9.png)



PCA yielded unclear results, requiring more indicators and data points to make a clear distinction between counties.   

![g3](https://user-images.githubusercontent.com/12026338/122307266-01991700-ced8-11eb-8646-19e9bd4eac5b.png)



