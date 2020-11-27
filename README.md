# ada-2020-project-milestone-p3-p3_splendids

## 1.	Title
**Safe Bitcoin Trading by Analyzing Weighted Signed Networks of Reviews**

## 2.	Abstract
A successful platform for cryptocurrency trading relies on the level of trust that is formed in between the two sides of a trade. The higher the number of successful trades, the higher the commissioning fee the platform earns. Having a bad experience on a platform may repel the current traders from the platform and also prevent new traders from joining the platform. Therefore, having a robust suggestion algorithm that can predict the outcome experience of a trade between users based on the ratings they’ve received before, will be of great benefit to the platform.
Since Bitcoin users are anonymous, there is a need to maintain a record of users' reputation to prevent transactions with fraudulent and risky users.

## 3.	Research Questions
As a result, we’re trying to answer the following questions:
~~~
Extracting the number of nodes and edges (total, positive, and negative), the ratio of positive and negative edges, and the total number of triads in the datasets.
Extracting the number of all positive triads representing the trust triangles. These triangles are one of the main sources of commissioning revenues.
Extracting the number of other types triads. We mainly want to prevent certain types of triads from being formed: ++- and ---. The former, because it will affect two of the three traders that already had a good experience (distrusts between the people that could be trusted) and the latter, because it deteriorates the reputation of the platform.
Is the model we are using to predict the relationships between the users robust enough? Is it over- or under- representing certain type of triads?
Is this over- or under- representing more towards the conservative approach (guaranteeing good experiences) or unconservative approach (causing bad experiences for trustable users)?
Using the weights presented in the datasets, does it improve the model accuracy to group the edges by (strongly positive, neutral, and strongly negative) and form the triads based on this new grouping method?
Does this new grouping method help guaranteeing good experiences?
~~~