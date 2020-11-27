# ada-2020-project-milestone-p3-p3_splendids

## 1.	Title
**Safe Bitcoin Trading by Analyzing Weighted Signed Networks of Reviews**

## 2.	Abstract
A successful platform for cryptocurrency trading relies on the level of trust that is formed in between the two sides of a trade. The higher the number of successful trades, the higher the commissioning fee the platform earns. Having a bad experience on a platform may repel the current traders from the platform and also prevent new traders from joining the platform. Therefore, having a robust suggestion algorithm that can predict the outcome experience of a trade between users based on the ratings they’ve received before, will be of great benefit to the platform.
Since Bitcoin users are anonymous, there is a need to maintain a record of users' reputation to prevent transactions with fraudulent and risky users.

## 3.	Research Questions
As a result, we’re trying to answer the following questions:

1) Extracting the number of nodes and edges (total, positive, and negative), the ratio of positive and negative edges, and the total number of triads in the datasets.
2) Extracting the number of all positive triads representing the trust triangles. These triangles are one of the main sources of commissioning revenues.
3) Extracting the number of other types triads. We mainly want to prevent certain types of triads from being formed: ++- and ---. The former, because it will affect two of the three traders that already had a good experience (distrusts between the people that could be trusted) and the latter, because it deteriorates the reputation of the platform.
4) Is the model we are using to predict the relationships between the users robust enough? Is it over- or under- representing certain type of triads?
5) Is this over- or under- representing more towards the conservative approach (guaranteeing good experiences) or unconservative approach (causing bad experiences for trustable users)?
6) Using the weights presented in the datasets, does it improve the model accuracy to group the edges by (strongly positive, neutral, and strongly negative) and form the triads based on this new grouping method?
7) Does this new grouping method help guaranteeing good experiences?

## 4.	Proposed dataset

1)	"soc-sign-bitcoin-otc " dataset from the Stanford Large Network Dataset Collection-- This dataset lets us know who-trusts-whom to trade using Bitcoin on a platform called Bitcoin OTC. Members of Bitcoin OTC rate other members in a scale of -10 (total distrust) to +10 (total trust) in steps of 1.
	* SOURCE: node id of source, i.e., rater
	* TARGET: node id of target, i.e., ratee
	* RATING: the source's rating for the target, ranging from -10 to +10 in steps of 1
	* TIME: the time of the rating, measured as seconds since Epoch
	
2)	"soc-sign-bitcoin-alpha " dataset from Stanford Large Network Dataset Collection. Same as the first dataset, this one lets us know who-trusts-whom to trade using Bitcoin on a platform called Bitcoin Alpha. Members of Bitcoin Alpha rate other members in a scale of -10 (total distrust) to +10 (total trust) in steps of 1. This dataset contains following columns:
	* SOURCE: node id of source, i.e., rater
	* TARGET: node id of target, i.e., ratee
	* RATING: the source's rating for the target, ranging from -10 to +10 in steps of 1
	* TIME: the time of the rating, measured as seconds since Epoch. 

## 5.	Methods
The two fundamental ingredients for conducting the investigation are: 1) large-scale datasets of signed review/relationship records between the Bitcoin traders of a platform, and 2) theories based on which the relationships within networks could be interpreted and forecasted

***Platforms to investigate:*** Bitcoin OTC and Bitcoin Alpha. Both of the datasets on the platform contain the data of who-trusts-whom to trade. Levels of trust are identified using a range of negative to positive integers.

***Theories for interpretation:*** balance theory which prefers prevalent cases of three mutual friends or two friends with a common enemy

***Analysis scenarios:*** undirected networks (directions of the links are not taken into account – for balance theory implementation) – It should be noted that networkx library can only count the triads in a directed graph! As a result, a directed graph shall be made in the python code while the rest of the tasks can be formed using the undirected graph theorems.

***Undirected network analysis:*** The occurrence and frequency of +++, +--, ++-, and --- triads are calculated in both existing and the randomly signed data. Also, a surprise value is provided, representing the deviation of the actual frequency from that of the random-shuffling model.

***Result interpretation:*** The goal is to maximize the number of successful trades in the platform to maximize the commissioning fees! This is achieved via supporting trustworthy users and limiting un-trustworthy ones! Furthermore, to keep the trustworthy users happy, the suggestion algorithm of a trade shall never propose an un-trustworthy person for a trade to trustworthy ones. The over- and under- presentation in the network model for certain types of extracted triads are interpreted as risk or value factor for the platform. Finally, the effects of trust level are also investigated both on the robustness and revenue guarantee of the model.

