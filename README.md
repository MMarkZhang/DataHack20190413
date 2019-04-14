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
Beijing Geolife.csv includes the trajectories of participants. Their locations in measure of Longitude and Latitude would be recorded every 3~5 seconds. 
![Data File Description](https://raw.githubusercontent.com/MMarkZhang/DataHack20190413/master/Visualization/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202019-04-14%20%E4%B8%8B%E5%8D%882.06.03.png)
_Five random samples from the Geolife dataset_   
![Beijing 5 samples](https://raw.githubusercontent.com/MMarkZhang/DataHack20190413/master/Visualization/Sheet%201.png)
**Participants from Beijing were travelling along the roads and might cluster in certain area.**   
  
 _Check out / Return counts density in each Austin Kiosk_ 
 ![Austin Checkout](https://raw.githubusercontent.com/MMarkZhang/DataHack20190413/master/Visualization/B-cycle-density-CheckOut.png)
 ![Austin Return](https://raw.githubusercontent.com/MMarkZhang/DataHack20190413/master/Visualization/B-Cycle-Return.png)
 
### Idea I 
Beijing might has similar population who need BCycle as Austin BCyclers have.   
#### Algorithm 

By using **K Means** on the data of Beijing Geolife
