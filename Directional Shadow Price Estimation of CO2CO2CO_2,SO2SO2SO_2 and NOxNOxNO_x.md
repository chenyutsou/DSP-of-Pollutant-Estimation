# Directional Shadow Price Estimation of CO<sub>2</sub>, SO<sub>2</sub> and NO<sub>x</sub>

## 1 Background and Motivation

## 2 Methodology

## 3 Example and Applications

Our objective is **ESTIMATION OF SHADOW PRICE** of by-product which is made by power plant. After building the model, we put real world data in our model to complete the empirical study. Our model have one input (Coal consumption), one good output (Electricity), and three bad output (CO<sub>2</sub>, SO<sub>2</sub>, and NO<sub>x</sub>).

### Data set

We use state level data of coal power plant from USA in 2000-2019. The total number of state is 48, because the data of 2 other state is not applicable. Our data is collect from [U.S. EIA website](https://www.eia.gov/). We merge emissions data (tons), electicity production (MWh), electricity price (dollar per MWh) and coal consumption (tons) as the data set . Please click [here]() for the data. Each worksheet is an annual data with 48 states.

Let's take a look at the raw data in 2019.
|Year|State|Coal|Electicity|CO2 Emissions|SO2 Emissions|NOx Emissions|Price|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|2019|AK   |555,952|683,055|1,399,888|1,928|2,156|202.165|
|2019|AL   |14,249,921|26,655,068|20,839,019|6,204|9,905|98.289|
|.....||||||||

### Choice of direction

Then, let us move to direction. According to C.Y., Lee's masterpiece (2015), the most robust direction vector is (.048, .508, .444).

As a result, we should assign the direction parameters like the block below.

    (g_C, g_S, g_N) = (.048, .508, .444)

We use this vector to project our raw data on the efficient frontier. Note that we should calculate the shadow price by efficient power plant. **Projecting step is very important.** 
After projecting step, we get the frontier data, and we need to plug frontier data into the first constraint (frontier constraint) in model (3).

### Tutorial step by step
哈哈哈哈哈

### Result of panel data analysis

The table below shows the statiscal information of shadow price during these two decades.

|Shadow price|CO2|SO2|NOx|
|:-|-:|-:|-:|
|MIN|$ 125|$ 5,222|$ 16,969|
|MEAN|624|17,866|68,118|
|MAX|1,229|57,987|186,211|

> Hint: We exclude the 2018 result, because it is an outlier and dominance all other years.

This figure shows the historical shadow prices of CO<sub>2</sub>. No obivous trend during two decades.

![](https://i.imgur.com/d4myGVk.jpg)

This figure shows SO<sub>2</sub>'s. The shadow prices before 2012 we calculate are more steady compared to those after 2012. Our guess is because of electricity prices go bumpy after that year.

![](https://i.imgur.com/ldPz6ka.jpg)

Finally, it's NO<sub>x</sub> turn. The shadow prices before 2012 we observed increased slowly.

![](https://i.imgur.com/Jxy7k5n.jpg)

## 4 Comments

After showing our empirical study, we have some topics need to discussion.

### Free disposal hull problem

### Outlier 2018

As we mentioned above, the shadow prices of three pollutants are outliers. The problem is because the spot price of coal from 5 main mining basin in U.S. rose dramatically that year. From the beginning of 2018 to ending, the coal price in U.S. increased almost 40%.

![](https://i.imgur.com/HAGXsOg.jpg)


### Distortion after 2012

Back to see our run chart again. No matter the pollutant is CO<sub>2</sub>, SO<sub>2</sub> or NO<sub>x</sub>, their run chart share the same pattern after 2012. Some exogenous variables had led to this distortion. It probably is because that the coal and electricity price had high variance during those years. Remember, according to our model, the shadow price computing is based on electricity price. The coal price influenced the electricity price, and in the end influenced the shadow price of pollutants.

### Our insight in real world

Echo to our beginning of study, the objective is providing insight of emission trading. Europe union has the most advanced and strictly enviroment protection policy. As this result, we compare our shadow price calculated with EU emission taxes.

|EU taxes|Amount ($/ton)|Shadow price|Amount ($/ton)|
|:-|:-:|:-|:-:|
|Carbon|47|Carbon dioxide|434|
|Sulpher|126|Sulpher dioxide|29,141|
|Nitrogen|249|Nitrogen oxide|81,097|

We see there is much room for EU to raise their emission taxes. We recommend them raising the taxes to transfer the bad part of externality into manufacturers' production cost. Another view of shadow prices far lager than taxes is because taxes are paid by one single company. However, the shadow prices of pollutant are bear by the whole social (that means everyone on earth). Actually, the shadow prices capture the numerical impact of these pollutant.

### Future work

The amount of **natural gas** using for power plant has exceed the amount of coal after 2015 in U.S. Due to coal comsumption having enviroment unfriendly result, U.S. has decide phase out the amount of coal use. In the future, the coal power plant percentage will drop to 0. We need to substitute our model input from coal to natural gas. Othewise, we will have some serious bias in our model. 



## Reference
