# Accenture North America Data Analytics and Visualization Job Simulation


## Project Understanding

### Project Brief

Social Buzz is a fast-growing social media company that has hired Accenture to help it handle the demands of its rapid expansion.


A 3-month initial project has been set up with the following key deliverables:


- An audit of their big data practice 
- Recommendations for a successful IPO
- An analysis of their content categories that highlights the top 5 categories with the largest aggregate popularity 


###  Accenture team

![team](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/51adfdda-eaf4-4dcf-bf28-e534392f7e8c)

The diagram above captures the Accenture team that has been assigned to this task.

With Mae Mulligan as the team lead, this team is broken into three parts. 


- Industry Experts: These people would enable the team to fully understand the industry context of the project.
- IPO Experts: These people would help provide the recommendations for the successful IPO
- Data Team: Members of this section of the team would help provide an audit of Social Buzz’s big data practice and analyze their content categories to identify the top 5 categories with the largest aggregate popularity.  


As the data analyst on this team, I have been tasked to carry out the content category analysis.

## Analysis Tools
Microsoft Excel was used for data cleaning, modeling, and subsequent analysis.


## Data Cleaning and Modeling

The client sent 7 datasets and a data model:

![model](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/58ce6af5-5b27-45db-b8f6-cc00852e107b)

The following activities were carried out to create a consolidated data model for analysis.

### Requirements gathering
Based on the business question being examined, datasets relevant to the project requirements were extracted from the list of datasets provided. The relevant business question is identifying the top 5 content categories with the largest popularity.
Relevant datasets are:
- Content
- Reaction
- ReactionType

### Data cleaning

For each dataset, the following were performed:


      1. Check for and eliminate duplicate data
      This was accomplished using 'Remove Duplicates' from 'Data Tools' in the 'Data' tab.

      2. Eliminate unnecessary columns:

      NOTE: Some columns not so relevant to identifying the top 5 content categories with the largest popularity were left in the data model to facilitate the creation of other strategic insights.


      Columns eliminated are identified below:

      - Content: 'User ID', 'URL', 'Untitled Row ID Column'
      - Reactions: 'User ID', 'Untitled Row ID Column'
      - ReactionType: 'Untitled Row ID Column'


Data cleaning operations specific to each dataset are identified next.

#### Content

1. Clean category column
Capitalization of Category entries was regularized, and Unwanted double quotes(“) were eliminated using 
      = LOWER(SUBSTITUTE(C2,"""",""))


![content category clean](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/a36b1c67-7863-4bee-ba5e-d23cb62b7e70)


2. The header for the 'Type' column was renamed to 'Content Type'


![content type](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/2cf790a8-1526-4b15-bd49-ed969aa362e5)

#### Reactions

1. Eliminated blank entries from the 'Type' column using the filter


2. The header for the 'Type' column was renamed to 'Reaction Type'

![reactions clean](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/64a7b1a2-1a6b-49d3-9d31-f86816c2a39d)


#### ReactionsType

1. The header for the 'Type' column was renamed to 'Reaction Type'


2. The data type of the 'Score' column was changed to numeric for easy analysis

![reaction type](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/96fa8ab3-c26d-4761-8dc8-bbe3af954eea)


### Data modeling
A consolidated data model was created to capture the relevant columns for analysis in a table.

This was done using various vlookup functions.

Using the reactions dataset as a base table, the following columns were added from their respective tables:

- From ReactionType dataset:

      Sentiment: =VLOOKUP(B2,ReactionTypes.xlsx!$A$2:$C$17,2,FALSE)

![sentiment](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/419d9b4d-d226-4fb6-bc4a-dddff7b388e9)

      
      Score: =VLOOKUP(B2,ReactionTypes.xlsx!$A$2:$C$17,3,FALSE)

![score](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/4eb21f00-84bc-482b-a010-db8be97e5544)


- From the Content dataset

Content Type: =VLOOKUP(A2,[Content.xlsx]Content!$A$2:$C$1001,2,FALSE)

![content type vlook](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/e3dfaf48-7a73-46d6-a973-6667959627a3)


Category: =VLOOKUP(A2,[Content.xlsx]Content!$A$2:$C$1001,3,FALSE)

![category vlook](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/284856b2-35bb-487b-a20e-d121b0a68e0a)


## Data Analysis

1. Most popular categories

A pivot table was used to calculate the top 5 most popular categories by the cumulative sentiment score.

![popularity pivot](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/4d02449d-e3d6-45d1-b204-e1433ecbeab4)

The top 5 categories are animals, science, healthy eating, technology, and food.


2. Number of unique categories and amount of reactions to the most popular category

The following pivot table was used to provide this additional information

![reactions pivot](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/2e52b31f-efcb-4a55-9be7-ecf18fdbcf55)


The number of unique categories is 16, and animal, the most popular category, had 1897 reactions.


3. Month with the least number of reaction

A pivot table was used to examine the number of reactions for each month.


![calendar](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/75f198bf-2412-4324-ba8c-c08a9699ab20)


February was the month with the least number of reactions (1914).

4. Most used reactions

The following pivot table was used to provide this additional information.


![reaction type pivot](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/63e98f7f-349e-4b5f-a38d-a03a819209c9)


The top 5 reaction types are heart, scared, peeking, hate, and interested.


## Data Visualization

1. Most popular categories

![category visual](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/5bd98804-6ff3-498a-ac67-b6982ad1bcea)

2. Most used reactions

![reaction type visual](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/1f098cca-0ed6-4f0e-bcbc-e344052c90e4)


## Actionable Insight 
1. Most Popular Category. 

![category visual](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/5bd98804-6ff3-498a-ac67-b6982ad1bcea)


The animal content category topped the charts with an aggregate popularity score of 74965. Its difference in popularity with the other categories is the highest in the top 5 content categories. This might indicate that the animal content category might continue to grow in popularity compared to the other categories. This might lead to a one-content-type platform, which might not be so desirable. To prevent this, the algorithm that controls the content users see should try to maintain an appropriate balance between content categories.


Looking at the other categories in the top 5 list, we see food and healthy eating. This indicates that a major portion of the audience may be interested in food content and, even more specifically, healthy food content. This healthy consciousness might also be generalized in other areas of their lives as healthy eating is more popular than food content. This can create an opportunity for collaboration with healthy eating brands to promote products and content on the platform


Science and technology being in the top 5 content categories might also show that the audience is looking for educational content they can learn from. This can indicate the potential benefit of partnering with science and technology content creators to facilitate the production of that type of content.


2. Month with the least number of reactions

February was identified as the month with the least number of reactions. Identifying posting patterns during this month would be cruicial to identifing a feasible course of action. If posting patterns indicate reduced activity. Content creation campaigns can be used to drive engagment on the platform for months associated with a low number of reactions.

For this to be done datetime data associated with when content is first uploaded could be collected to fascilitate analysis and subsequent data driven decision making.


3. Most Used reactions

![reaction type visual](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/1f098cca-0ed6-4f0e-bcbc-e344052c90e4)

It should be noted that 2 of the top 4 reactions are scared and hate. It might not be so great to spread content promoting such reactions on the platform.


Investigating further by taking a sample of content with these reactions and examining what they are might help understand how best to handle the situation. 


## What’s Next

The insights gained from this analysis can be extended by examining real-time data generated on the platform for even more timely data driven decision making.

Other areas of the organization can also be analyzed to improve company-wide efficiency and performance. 

In accordance with these possibilities, the datasets were analyzed using Power BI. A content analysis dashboard was created to show the potential for real time analytics and further extraction of insights with the right data analysis framework.

Dashboard

![dashboard](https://github.com/Jucodez/Accenture-North-America-Data-Analytics-and-Visualization-Job-Simulation/assets/102746691/47b54c7c-9b93-4687-853f-0bb2b496812b)


## Conclusion 

Overall, this data analysis project enabled the relevant stakeholders at Social Buzz to gain valuable insight into the content and users of their platform. It also displayed the potential of a comprehensive data analytics framework and the benefits the company would gain by working with Accenture.
