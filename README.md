**Quantile Trading**

**Objective** -  Study the performance of quantile trading strategy on 200 stocks based on beta neutral approach. 

**Data** - 
*Entire dataset is downloaded from Zacks fundamental database available for free on Quandl website.*
The data is downloaded for dates Jan 2011 through Jan 2018. 200 stocks are chosen from the universe of US equities satisfying the following requirements - 

- End-of-day adjusted closing prices are available
- The debt to market cap ratio is greater than 0.1 at least once over the investment period
- The stock does not belong to automotive, financial or insurance sector
- The data is available regarding total debt, book value per share & diluted net earnings per share, no more than one year old

**Select Financial Ratios** - 
We will work with the following ratios - 
1. debt to market cap
2. price to book
3. price to earnings

**Strategy** - 

Divide the stocks into deciles based on financial ratios. 
<br>
For constant position sizes, we take a long position on 1<sup>st</sup> decile stocks and a short position on 10<sup>th</sup> decile stocks. 
<br>
For variable position sizes, we take position on all deciles with variable sizes starting from 1(on 1<sup>st</sup> decile) to -1(on 10<sup>th</sup> decile).
<br>
Each position on a security S is made beta neutral using the approach explained in the following section.

**Beta neutral** - 
For each position in a security S, as of a given simulation date d, perform an ordinary least squares linear regression of its daily returns on adjusted close prices to those of SPY ETF over the previous calendar month. The regression equation can be written as follows - 

>> r<sub>S</sub> = b<sub>0</sub> + b<sub>1</sub> * r<sub>SPY</sub>

To achieve beta neutrality, we assume that in addition to $x of this security, portfolio also takes on a position of -$b<sub>1</sub>x in the SPY ETF. 

**Analysis** - 

