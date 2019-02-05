# 99co

The Jupyter notebook "web scraping - 99co" contains code to extract property data from 99.co, a website where HDB flats are listed for sale. I used Selenium WebDriver to interact automatically with the website, and BeautifulSoup to parse HTML. I extracted the following information from the website: address, type of HDB flat, year built, sale price, number of bedrooms, number of bathrooms, price per square foot, and property size (in square feet). A total of 9600 property listings were scraped from the website.

The Jupyter notebook "analysis - 99co" contains code to process and analyze the scraped data. First, I cleaned some of the variables before converting them to numeric variables. Next, I dropped observations with missing values and extreme outliers. I then plotted some data visualizations, which confirmed that larger and newer properties tend to have higher prices. Indeed, correlation analysis reveals that the variable most strongly correlated with property price is property size (correlation coefficient = 0.59).

I then split the dataset into training and test sets, trained a random forest to predict the prices of HDB flats based on all available property attributes (other than price per square foot), and evaluated the performance of the model on the test set. The random forest model achieved a RMSE (root mean squared error) of $107743 and a MAPE (mean absolute percentage error) of 13.7% on the test set. In comparison, a simplistic approach that always used the mean price of the training set as the prediction would achieve a RMSE of $171350 and a MAPE of 31.4%.

To improve the performance of the predictive model, one could include other relevant features such as proximity to amenities and which floor the HDB flat is on.
