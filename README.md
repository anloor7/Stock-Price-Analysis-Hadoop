# Max-Min-StockPrice-Analysis-Hadoop

- This repository contains Stock value analysis for indivisual stock's max and min value.. 
- Used Hadoop MapReduce, pig and Hive to analyse stock values.
- Deployed hadoop on AWS and execute all three application on Amazon AWS.


#### Hadoop MapReduce

1. Submit Job
``` 
hadoop jar /niket/mapreduce/stocks/StockPriceAnalysis.jar com.stock.maxcloseprice.MaxClosePrice /user/niket/input/stocks output/mapreduce/stocks
```

2. View Result
```
hadoop fs -cat output/mapreduce/stocks/part-r-00000
```


#### Pig

1. Submit Pig Script
```
pig /niket/pig/stocks/max-closeprice.pig
```

2. View Result
```
hadoop fs -cat output/pig/stocks/part-r-00000
```





## Results

1. Hadoop MapReduce
- screenshot 1

![Screen Shot 1](https://github.com/niketpatel2525/Stock-Price-Analysis-Hadoop/blob/master/4.%20screenshots/hadoop%20(1).png)

- screenshot 2

![Screen Shot 2](https://github.com/niketpatel2525/Stock-Price-Analysis-Hadoop/blob/master/4.%20screenshots/hadoop%20(2).png)

- screenshot 3

![Screen Shot 3](https://github.com/niketpatel2525/Stock-Price-Analysis-Hadoop/blob/master/4.%20screenshots/hadoop%20(3).png)