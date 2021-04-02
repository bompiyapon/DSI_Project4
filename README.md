# DSI_Project4 West Nile Virus Prediction
Predict West Nile virus in mosquitos across the city of Chicago

## Problem Statement
----------------------------
Previously on 2005 in Sacramento Country cost approximately 
total economic impact of WNV was $2.98 million we try to minimize number of infected and false predicting lead to increasing number of infected.


## Executive Summary
----------------------------
West Nile virus is most commonly spread to humans through infected mosquitos. Around 20% of people who become infected with the virus develop symptoms ranging from a persistent fever, to serious neurological illnesses that can result in death.

In 2002, the first human cases of West Nile virus were reported in Chicago. By 2004 the City of Chicago and the Chicago Department of Public Health (CDPH) had established a comprehensive surveillance and control program that is still in effect today.

With the problem statement we will try to predict which trap the WNV will present therefore, we can preventing by spray the pesticide to save the economic costs and also do some cost-benefit analysis

### Key Takeaways
----------------------------
- WNV is highly seasonal, most occur in July and August (week21-week32)
- WNV outbreak are more serious in summer (high temperature) and high perciption (humidity, dewpoint, etc.)


### Data Dictionary
----------------------------
1. train.csv - contain the number of trap in Chicaco
2. test.csv - file which have almost same column with train don't have only wnvpresent (which we use to predict) and nummosquitos

| Feature | Type   |Description |
|----|----|----|
|Date     | object | Date of the case |
|Address  | object | Address of trap |
|Species  | object | Species of mosquitos |
|Block    | int64  | Block of trap |
|Street   | object | Street of trap |
|Trap     | object | Unique ID of trap |
|AddressNumberAndStreet| object | Address of trap |
|Latitude | float64 | Latitude of trap |
|Longitude| float64 | Longitude of trap |
|AddressAccuracy   | int64 | Accuracy of measurement (lat/long) |
|NumMosquitos  | int64 | Number of mosquitos found in trap |
|WnvPresent | int64 | 0 - Mosquitos in trap not have WNV / 1 - Mosquitos in trapdo have WNV |

3. weather.csv - the weather across 2007 to 2014 contain weather data of 2 station in Chicaco

| Feature | Type   | Description |
|----|----|----|
|Station  | int64  | Number of weather station in Chicago 1 or 2 |
|Date     | object | Date of weather measurement |
|Tmax     | int64  | Highest temperature in that day (in fahrenheit) |
|Tmin     | int64  | Lowest temperature in that day (in fahrenheit)  |
|Tavg     | object | Average temperature in that day (in fahrenheit)  |
|Depart   | object | Measure of climate change but tells us nothing about the effects of climate change.|
|Dewpoint | int64  | Temperature to which air must be cooled to become saturated. |
|Wetbulb  | object | A measure of the heat stress in direct sunlight, which takes into account: temperature, humidity. |
|Heat     | object | Measure of how hot it really feels when relative humidity is factored in with the actual air temperature. |
|Cool     | object | Measure of how cool it really feels when relative humidity is factored in with the actual air temperature. |
|Sunrise  | object | Time of sunrise |
|Sunset   | object | Time of Sunset |
|CodeSum  | object | Event that occur in that day such as snow, duststrom, and etc. |
|SnowFall | object | Height of snow from ground |
|PrecipTotal | object | Measurement of water – rain / snow / blizzard / etc. |
|StnPressure | object | Air pressure |
|SeaLevel | float64 | Air pressure at sealevel |
|ResultDir| int64 | Wind direction |
|AvgSpeed | object | Average speed of wind |


4. spray.csv - contain date which spray the pesticide and latitude / longitude

| Feature | Type   | Description |
|----|----|----|
|Date | object | Date of spray |
|Time | object | Time of spray |
|Latitude | float64 | Latitude of spary |
|Longitude| float64 | Longitude of spray |

### Conclusion
----------------------------
Our model correctly predicts 77.8% of the observations
- Among posts that our model predicted, Sensitivity 92% (False Negative 161 which is have WNV but predicted not have WNV)

Conclusion
- WNV is highly seasonal, most occur in July and August (week21-week32)
- WNV outbreak are more serious in summer (high temperature) and high perciption (humidity, dewpoint, etc.)

Scope for future improvements:
- Try other ensemble models, such as using boosting , SVM
- Ability for model to classify more than two subreddits
- Improve the false positive value (predicted LoL as DotA)
