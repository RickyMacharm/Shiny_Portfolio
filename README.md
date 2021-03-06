# Shiny_Portfolio
Portfolio Management

This R program use Shiny Dashboard to manage a portfolio of financial instruments.  
At the moment, the program is based on a "transaction.csv" file where all the transactions takes place.  Go check the [transaction.csv](../master/transaction.csv) file to see how it is organized.  It is the base from which all computations are made.  
The price of all the financial instruments are saved as "hard" data in a separate folder as .csv files.  

A couple of reason for this: faster time when creating chart of the financial instruments (server does not have to download the historical data from another place every time a call is done to it) and because of this less load on the provider of free data such as alphavantage which is the one we are using.  The downside of this choice is that we have to download regularly (daily, weekly) the data and store it.  

To download the historical data of the financial instruments we use the file [get_data.r](../master/get_data.r).  The code has been adapted from [thertrader](http://www.thertrader.com/2015/12/13/maintaining-a-database-of-price-files-in-r/) blog.  I use alphavantage, don't forget to use your own API key (I took off mine on this file). 

At the moment, you can have 
* have multiple currency (although it has only limited functionality at the moment)
* have multiple brokers (in the sense that you prortfolio is comprise of sub-portfolio / account)
* various financial operations such as: equity, stocks, etf, dividends, fees and forex
* have short positions

HOWTO run the program
1.  Create a new folder call it whatever like "my_portfolio".  
2.  Make your own "transaction.csv" file with your own instruments.  Put that file in your "my_portfolio" folder.  
3.  Create a folder "financial_data" where all the historical data of your instrument will be stored.  You can use the [get_data.R](https://github.com/fderyckel/Shiny_Portfolio/blob/master/get_data.r) file to do so.  
5.  Make sure you have all the essential libraries installed on your machine: tidyverse, quantmod, TTR, lubridate, plotly, shinydashboard, (and to come: [RollingWindows](https://github.com/andrewuhl/RollingWindow)
4. Put the get_data.r file in your "my_portfolio" folder and run the script.  Read the [quantmod](https://github.com/joshuaulrich/quantmod) doc to adapt the script to your particular case using Yahoo, Google or Alphavantage.  
5. Now you can run app.r file ;-) 


I'm looking for a job in the financial sector where I can flex my data science / statistics skills.  You can find more about me on [my Linkedin](https://www.linkedin.com/in/francois-de-ryckel/) and on my [blog](https://fderyckel.github.io/aboutme/) page.  Thanks. 
