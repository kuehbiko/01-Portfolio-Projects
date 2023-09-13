# Lyft Baywheels 2022 Analysis

## Project Overview
In this project, we analyzed Lyft Baywheels trip data from 2022 and suggested measures that could be taken to improve the experience of Baywheels users and increase customer satisfaction.

## Business Understanding
We approach this analysis from the point of view of the operators of the Baywheels rideshare program, Lyft, to understand the different types of Baywheels bike users, and how the company can better cater to the needs of each user group, and as a whole.

To achieve this, we aim to answer the following questions:
1. Do the needs of the customers differ by membership type? How do they differ and how can the company cater to these needs?
2. Do the needs of the customers differ by the type of bike they use? How do they differ and how can the company cater to these needs?
3. At which stations can Lyft focus more on rebalancing efforts to alleviate bike shortage for Baywheels users?

**What is rebalancing?** \
Rebalancing is an optimization problem that refers to meeting demand at certain stations by relocating them and temporarily increasing station capacity, and is a key challenge faced by operators providing such rideshare services [[1](https://people.orie.cornell.edu/shane/pubs/BSOvernight.pdf)].  

In the most common approach, trucks are used to move bikes to high-demand areas. This is particularly effective overnight, when both traffic and demand are low. During the day, vehicular traffic impairs these
efforts, and instead operators use trikes to transport a smaller number of bikes across stations, or corrals to artificially increase the capacity of stations.

The optimization of rebalancing is a complex problem that we will only briefly touch on in this analysis.

**Summary of Findings** \
Overall, our findings can be summarized thus:
1. Subscribers are more likely to use the bikes for short distances during peak hours on weekdays. Non-subscribers prefer to use bikes for leisure during offpeak hours and on weekends. Thus the company may provide fast and reliable electric bikes for members, and comfortable classic bikes for casual users
2. Electric bikes are utilized for longer distances, accruing greater mileage in a shorter period of time and thus may be more prone to wear and tear. The company may wish to check on the condition of these bikes more often.
3. Page St at Masonic Ave and Leavenworth St at Broadway stations have the greatest deficit in bikes at the end of the day. More docks can be placed at these stations, and more bikes can be allocated to these stations during rebalancing overnight.


## Data Understanding
The dataset used contains records of individual rides made via a bike-sharing system covering the greater San Francisco Bay area in 2022. It provides details of each ride, such as a unique ride ID, start and end stations, start and end coordinates, bike type and membership type.

The data is made up of over 2.5 million rows of data. Of this 2.5 million, 400,000 rows were missing the start, end, or both stations of trips, and 2000 rows were missing endpoint coordinates.

The original data is available on [Lyft's System Data page](https://www.lyft.com/bikes/bay-wheels/system-data).

## Analysis
Here are some of the most notable trends we found:

There are more trips by members on weekdays, and more trips by casual users on weekends. By tallying both, we can see that the number of trips are higher during the weekdays and lower during the weekends. Conversely, median duration of trips are lower during the weekdays and higher during the weekends
![newplot (28)](https://github.com/kuehbiko/01-Portfolio-Projects/assets/88494428/105becf9-8d8b-4849-8d4b-dfb987a8c690)
![newplot (29)](https://github.com/kuehbiko/01-Portfolio-Projects/assets/88494428/723f7d58-df3a-46b7-a031-ca42ee452928)

For all days, members have shorter trips (both duration and distance) than casual users on all days.
![newplot (30)](https://github.com/kuehbiko/01-Portfolio-Projects/assets/88494428/66fabcb9-d6cb-47b9-b17d-171a158b5706)

The usage by members are clustered around peak hours while casual usage is more spread out over the day.
![newplot (31)](https://github.com/kuehbiko/01-Portfolio-Projects/assets/88494428/5e7082f4-8b81-4076-8fdf-07668478b7c3)

65% of rides use electric bikes, 35% use classic bikes, less than 0.001% use docked bikes. However, there is no significant preference of either type of bike. The median duration of a classic bike trip is longer on the weekends. The median sitance of an electric bike trip is longer than the median distance of a classic bike trip for all days.
![newplot (32)](https://github.com/kuehbiko/01-Portfolio-Projects/assets/88494428/2685f4cb-b94c-4919-a47f-9001b656b945)
![newplot (33)](https://github.com/kuehbiko/01-Portfolio-Projects/assets/88494428/557a82f0-fc6f-4b7f-abb8-6365ac43d14b)

The top 10 stations with the most outgoing traffic are also the stations with the most incoming traffic and likewise for the stations with the least traffic. \
Over the week, he demand for bikes are greatest at Page St at Masonic Ave and Leavenworth St at Broadway and the supply of bikes are greatest at North Point St at Polk St on the weekends. \
The demand for bikes are the greatest at Howard St at Beale St, Salesforce Transit Center (Natoma St at 2nd St) and Post St at Kearny St on the weekdays at 5pm. Likewise the supply of bikes are greatest at these 3 stations at 8am

## Conclusions
**Do the needs of the customers differ by membership type? How do they differ and how can the company cater to these needs?**

The preferences of members and casual users are significantly different. Trips by members are shorter and more frequent during the peak hours of weekdays, while casual customers prefer trips that are longer and during off-peak hours or weekends. We can infer that most members are working adults or college students with a fixed schedule and need for reliable transportation. Casual customers on the other hand are more likely to make a trip out of convenience or spontaneity. Our data suggest their usage is more for leisure or enjoyment and not necessity.

We recommend providing more electric bikes to members for speed and efficiency, and more classic bikes to casual users.

We also recommend that targeted ad campaigns towards members and casual users differ in the kinds of promotions being offered. For example, members might be more likely to enjoy a discount on recurring monthly subscriptions while casual users might be more likely to enjoy one-time promotions.

**Do the needs of the customers differ by the type of bike they use? How do they differ and how can the company cater to these needs?**

There is no significant preference for the type of bike provided by the service. As there is no significant difference in preference for electric and classic bikes, we have no recommendation to provide more of either type of bike as a whole. However, we recommend the company keep in mind the ratio of electric and classic bikes across stations when doing daily rebalancing. For example, more electric bikes can be distributed to stations that are frequented during weekday peak hours (such as Howard St at Beale St, Salesforce Transit Center (Natoma St at 2nd St) and Post St at Kearny St) to cater to working adults, while classic bikes can be distributed to stations near parks.

Electric bikes accrue a higher mileage than classic bikes across all days of the week. Due to heavily usage, electric bikes may be at a higher risk of wear and tear compared to classic bikes. Therefore we would recommend that maintenance for electric bikes occur more frequently than classic bikes.

**Are there certain stations that should be targeted for overnight rebalancing?**

In terms of rebalancing, the demand for bikes are greatest at Page St at Masonic Ave and Leavenworth St at Broadway. The company could take this into account during overnight rebalancing to provide more bikes to this station. Also, there is often a surplus of bikes at North Point St at Polk St. For efficient rebalancing, the company may consider funneling bikes from this station to stations with high daily demand.

**Next Steps** \
Given the true location of each station and the cost of transporting bikes, there is an opportunity to optimize the rebalancing process of bikes, both overnight and during the day. This will allow the company to efficiently allocate resources to the rebalancing of bikes at each station with greater precision of the exact hour and minute when demand is the greatest (at the moment, we only have an estimate).

We may also wish to further explore the preferences of members and casual users through binary classification techniques. This will allow us to identify the features that are most strongly associated with subscribers. This way, the company may be able to identify casual users that have to potential to become members. The company may then be able to send such users targeted adviertisements to convince them.

## References:
1.
