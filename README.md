# Max-Min-StockPrice-Analysis-Hadoop

- This repository contains Stock value analysis for indivisual stock's max and min value.. 
- Used Hadoop MapReduce, pig and Hive to analyse stock values.
- Deployed hadoop on AWS and execute all three application on Amazon AWS.


#### Hadoop MapReduce

1. Submit Job
``` 
$ hadoop jar /niket/mapreduce/stocks/StockPriceAnalysis.jar com.stock.maxcloseprice.MaxClosePrice /user/niket/input/stocks output/mapreduce/stocks
```

2. View Result
```
$ hadoop fs -cat output/mapreduce/stocks/part-r-00000
```


#### Pig

1. Submit Pig Script
```
$ pig /niket/pig/stocks/max-closeprice.pig
```

2. View Result
```
$ hadoop fs -cat output/pig/stocks/part-r-00000
```

#### Hive

1. Enter into Hive shell
```
$ hive
```
2. Run all the Hive queries from the source file.

#### Spark
1. ENter into spark-shell
```
$ spark-shell --master spark://node1:7077
```
2. Run all scala instruction in spark shell
```
scala> val stocks = sc.textFile('/user/niket/stocks-datasets')
scala> val splits = stocks.map(record => record.split(","))
scala> val symbol = splits.map(arr => (arr(1), arr(7).toInt))
scala> val maxvol = symbol.reduceByKey((vol1, vol2) => Math.max(vol1,vol2))
scalla> maxvol.collect().foreach(println)
```

## Results

Sample Input

![Sample Input](https://github.com/niketpatel2525/Stock-Price-Analysis-Hadoop/blob/master/4.%20screenshots/sample%20input.png)

1. MapReduce
- screenshot 1

![Screen Shot 1](https://github.com/niketpatel2525/Stock-Price-Analysis-Hadoop/blob/master/4.%20screenshots/hadoop%20(1).png)

- screenshot 2

![Screen Shot 2](https://github.com/niketpatel2525/Stock-Price-Analysis-Hadoop/blob/master/4.%20screenshots/hadoop%20(2).png)

- screenshot 3

![Screen Shot 3](https://github.com/niketpatel2525/Stock-Price-Analysis-Hadoop/blob/master/4.%20screenshots/hadoop%20(3).png)

2. Pig

- Screenshot 1

![Screen Shot 1](https://github.com/niketpatel2525/Stock-Price-Analysis-Hadoop/blob/master/4.%20screenshots/pig%20(1).png)

- Screenshot 2

![Screen Shot 2](https://github.com/niketpatel2525/Stock-Price-Analysis-Hadoop/blob/master/4.%20screenshots/pig%20(2).png)

- Screenshot 3

![Scree Shot 3](https://github.com/niketpatel2525/Stock-Price-Analysis-Hadoop/blob/master/4.%20screenshots/pig%20(3).png)

3. Hive

- Screenshot 1

![Screen Shot 1](https://github.com/niketpatel2525/Stock-Price-Analysis-Hadoop/blob/master/4.%20screenshots/Hive%20(1).png)

- Screenshot 2

![Screen Shot 2](https://github.com/niketpatel2525/Stock-Price-Analysis-Hadoop/blob/master/4.%20screenshots/Hive%20(2).png)

- Screenshot 3

![screen Shot 3](https://github.com/niketpatel2525/Stock-Price-Analysis-Hadoop/blob/master/4.%20screenshots/Hive%20(3).png)