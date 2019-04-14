## DataHack20190413
 Data Hackthon - Dataset (BCycle.csv & Beijing Geolife.csv)
### Team Members
 - Binglin(Mark) Zhang 
 - Zijian(Steven) Wang 
 - Fei He 
### Objectives 
Introducing BCycle into Beijing in 2008.   
How would it leverage the efficieny?  
Would it improve the air condition?   
What kind of memeberships will people purchase?  
### Background Information from Data
#### Beijing Geolife dataset 
Beijing Geolife.csv includes the trajectories of participants. Their locations in measure of Longitude and Latitude would be recorded every 3~5 seconds. 
![Data File Description](https://raw.githubusercontent.com/MMarkZhang/DataHack20190413/master/Visualization/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202019-04-14%20%E4%B8%8B%E5%8D%882.06.03.png)
_Five random samples from the Geolife dataset_   
![Beijing 5 samples](https://raw.githubusercontent.com/MMarkZhang/DataHack20190413/master/Visualization/Sheet%201.png)
**Participants from Beijing were travelling along the roads and might cluster in certain area.**   
  
#### Austin BCycle Dataset
![Austin BCycle1](https://raw.githubusercontent.com/MMarkZhang/DataHack20190413/master/Visualization/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202019-04-14%20%E4%B8%8B%E5%8D%882.06.16.png)
![Austin BCycle2](https://raw.githubusercontent.com/MMarkZhang/DataHack20190413/master/Visualization/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202019-04-14%20%E4%B8%8B%E5%8D%882.06.27.png)
 _Check out / Return counts density in each Austin Kiosk_ 
 ![Austin Checkout](https://raw.githubusercontent.com/MMarkZhang/DataHack20190413/master/Visualization/B-cycle-density-CheckOut.png)
 ![Austin Return](https://raw.githubusercontent.com/MMarkZhang/DataHack20190413/master/Visualization/B-Cycle-Return.png)
 
### Idea I 
Beijing might has similar population who need BCycle as Austin BCyclers have.   
Why not introduce BCycle into Beijing.

#### Algorithm 

By using **K Means** on the data of Beijing Geolife, we cluster the footprints into 100 groups. And each group has a center which represents the potential kiosk station.  
_100 stations_
![100 kiosks](https://raw.githubusercontent.com/MMarkZhang/DataHack20190413/master/Visualization/WechatIMG178.jpeg)
_Closer Look_
![closer look](https://raw.githubusercontent.com/MMarkZhang/DataHack20190413/master/Visualization/WechatIMG179.jpeg)
Some kiosks are only 10 meters from each other, which indicates these locations need more bikes and a potential higher frequency of CheckOut/Return.

### Idea II
Will BCycle in Beijing benefit people? 
#### Austin BCycle data tells us 
_Two Distribution Graph_
![](https://raw.githubusercontent.com/MMarkZhang/DataHack20190413/master/Visualization/Trip%20Duration%20Minutes%20distribution(after%20clean%20outliers).png)
![](https://raw.githubusercontent.com/MMarkZhang/DataHack20190413/master/Visualization/WechatIMG176.png)
We were thinking if there is a correlation between Distance vs. Duration? 
We tried to predict duration by distance, but find big discrepancy. 
Then we attempted to visualize this: 
_The number of times bikes were used (vs. weekday and hour in a day)_ 
![](https://raw.githubusercontent.com/MMarkZhang/DataHack20190413/master/Visualization/weekday-time-usage.png)
#### Algorithm 
We build a model to predict the **duration** of a bike ride (by **distance, weekday, check out time**), by using xgboost. 
