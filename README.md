The transition to a fully renewable energy production is a current challenge for the German society.
At the moment on a year’s average about 40% of the energy produced in Germany is renewable.
And it needs to and will be more in the future.

Well, the renewable energy production is very volatile and depends mostly on the weather. On the
other hand grid operators need to keep the network balanced to prevent blackouts, which means that
the energy production must meet the energy consumption at any time. Knowing how much energy
will be produced helps to better plan how much energy needs to be produced by other, not
renewable, power plants at the moment. In future it may help to better plan energy storage
capacities and usage of stored energy or even flexible consumption of energy.


Data description:
I want to train a model that will predict the hourly renewable energy production in Germany for one
day using the weather prediction for that day.
In order to do so, I will include historical hourly weather data of the past 24 months and the hourly
energy production data for the same period of time. The weather can vary in different regions of
Germany. Most of the wind turbines are located in the North, West and East of Germany, whereas
most of the solar power is produced in the South and East of Germany. For this reason, I will
include the historical weather data of four weather stations: one in the North, South, West and East
respectively.

The historical weather data to train the model will be taken from https://meteostat.net/de/. This is a
platform that collects weather and climate data and makes it available via a python library called
meteostat. 

The most promising features are wind speed, wind direction, sunshine total in minutes (m),
precipitation total in mm, peak wind gust in km/h, since the wind power generation depends on the
wind and the solar power generation depends on the sunshine. Since I want to include the data of
four weather stations, it means that I will have 5 * 4 = 20 weather features in total.

The target variable is the hourly total amount of renewable energy production. The historical energy
production data is provided by the German Federal Network Agency for Electricity. At its’ website
the Power generation data for all generation units with an installed generation capacity of at least
100 MW can be downloaded in csv format and can be stored and used free of charge. 4 The sum of
the power generation by ‘Biomass’, ‘Hydropower’, ‘Wind offshore’, ‘Wind onshore’,
‘Photovoltaics’ and ‘Other renewable’ is the total amount of renewable energy production.
