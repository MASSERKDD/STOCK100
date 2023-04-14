# STOCK100 - A Dataset for Stock Market Analysis

We collected recent stock data from S&P 100 stocks between 2017 and 2022 and named it as STOCK100. 

**Features**

Compared to Stocknet and KDD17, STOCK100 has the following characteristics  :

1. Up-to-date: The STOCK100 dataset comprises open, close, volume, high, low, and adjusted close prices for 100 stocks that were traded between January 3rd, 2022 and December 30th, 2022. 
2. More challenging: The dataset covers a period that includes several major international events that have caused significant disruptions to financial markets, resulting in more domain shifts between training and test sets. These events include but are not limited to the Trump administration's tax reform at the end of 2017, the US-China trade dispute in early 2018, three circuit breakers triggered in the US stock market in March 2020, the Federal Reserve's tightening in November 2021, and the Russia-Ukraine conflict in February 2022.
3. More flexible test split: We employed a flexible train-test split, with data from January 4th, 2017 to December 31st, 2021 used as the training set, data from January 3rd, 2022 to May 31st, 2022 as the initial test set, and data from January 3rd, 2022 to December 30th, 2022 as the extended test set * . The extended test set* has a longer time span of almost a year compared to the initial test set, allowing for testing of a model's ability to adapt to updates in an online setting over time.

**Data processing**

All original data can be found in Data directory. We have normalized all the stock data features in STOCK_ARRAY.npz. More detail about can be fond below.  Additionally, we provide two lists a.STOCK50.txt, which includes a subset of 50 stocks and b. STOCK100.txt, which includes all 100 stocks.

```python
{
    stock_array:stock_array, #(100, 1510，6) stocknum=100 stock_length=1510 normalized_feature=6 
	volume_mean:volume_mean, #volume mean
	volume_std:volume_std, #volume std
	mask:masks, #list of list [[(start_index,end_index)],[],[]] len(masks)=stocknum
    stocknames:stocknames, #list
    column_names:column_names, #name of six columes of stock_array
    dates:dataes,#dates list
}
```
