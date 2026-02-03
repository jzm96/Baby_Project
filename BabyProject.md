```python
import pandas as pd
import matplotlib.pyplot as plt
```


```python
df = pd.read_csv('precious_metals_historical_data.csv')
```

## Graph 1 - Precious Metal Prices Over Time


```python
df['Date'] = pd.to_datetime(df['Date'])
plt.figure(figsize=(12,6))
plt.plot(df['Date'], df['Silver_Price'], label='Silver', alpha=0.8)
plt.plot(df['Date'], df['Gold_Price'], label='Gold', alpha=0.8)
plt.plot(df['Date'], df['Platinum_Price'], label='Platinum', alpha=0.8)
plt.title('Precious Metals Prices (2016-2023)')
plt.xlabel('Date')
plt.ylabel('Price ($)')
plt.legend()
plt.grid(True, alpha=0.3)
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```


    
![png](output_3_0.png)
    


### This graph shows us the price of Silver, Gold and Platinum. Beginning in 2016 through 2026.

## Graph 2 - Gold/Silver Ratio 


```python
plt.figure(figsize=(12,6))
plt.plot(df['Date'], df['Gold_Silver_Ratio'])
plt.title('Gold/Silver Ratio Over Time')
plt.ylabel('Ratio')
plt.grid(True, alpha=0.3)
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```


    
![png](output_6_0.png)
    


### This graph (2) shows the ratio of Gold and Silver. Beginning in 2016 through 2026.

## Summary Price Table


```python
price_summary = df[['Silver_Price', 'Gold_Price', 'Platinum_Price']].agg(['mean', 'std', 'min', 'max']).round(2)
price_summary['unit'] = '$/oz'
print(price_summary)
```

          Silver_Price  Gold_Price  Platinum_Price  unit
    mean         21.43      173.90           93.07  $/oz
    std           9.15       64.56           18.82  $/oz
    min          11.21      107.34           55.36  $/oz
    max         105.60      495.90          252.25  $/oz
    

### This summary gives us the statistical information such as the mean, std, min and max of the three precious metals in dollars per ounce.

## Datasets like this are very helpful for those that choose to invest in precious metals for the long term. We can also use datasets like this to predict future prices for said precious metals.

#### **AI was used to help generate the graphs


```python

```
