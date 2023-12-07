# MGT4250 Fall 2023 Course Project
Author: Hannah Gneco, hgneco@elon.edu

## Project Description

[Link to Tableau Public Visualization](https://public.tableau.com/views/MGT4250CourseProject/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link)

### Questions of interest
1. Which states have received the highest and lowest median ratings?
2. Is there a difference in the items purchased between the gender and/or average age?
3. Which products are purchased more often each month?

### Importance
This is *especially* **important** because
 1. By knowing which states will both the highest and lowest median rating it will determine which states may need more promotions.
 2. If there is a difference in the items purchased by the average age your company will be able to determine their target age group and/or gender for the future. In addition, you can detemine whether the average age differs between the male and female. 
 3. You can determine the item purchased that generated the highest total purchase amount and during which season. You can promote during the specifc season and/or for the item purchased.

## Data Description
In order to access the data you must download the "shopping_trends_updated.csv" file from Kaggle. After you download the file, open Tableau Desktop application and connect the csv file. The "shopping_trends_updated.csv" dataset consists of 18 columns with different demographic, geographic, and sales information. The columns I used within this project were Age(average), Gender, Purchase Amount(total), Review Rating(median), Items Purchased, and Season. 

## Interpreting Visualizations
Visualization 1 - By creating this visualization I have found the locations that have the highest/lowest review ratings in order to improve service.
High: Wisconsin and Maine with median=4
Low: West Virginia and New Hampshire with median=3.5

Visualization 2 - This visualization shows us how the average age that purchased each item differs by gender.
There is no significant difference of the average ages by gender and item purchased. 
Max = ~7 male(boots) 
Min = 0.004 male(pants)

Visualization 3 - This visualization tells us which items were essentially purchased more per season.
In the Fall the item that generated the highest purchase total = $3,224 (hats)
In the Spring the item that generated the highest purchase total = $3,145 (sweaters)
In the Summer the item that generated the highest purchase total = $3,006 (jewelry)
In the Winter the item that generated the highest purchase total = $3,105 (shirt)


## Discussion & Summary

An article from the Knowledge at Wharton, *[Men Buy, Women Shop’: The Sexes Have Different Priorities When Walking Down the Aisles](https://knowledge.wharton.upenn.edu/podcast/knowledge-at-wharton-podcast/men-buy-women-shop-the-sexes-have-different-priorities-when-walking-down-the-aisles/)*, describes the different shopping habits between gender. The term "men buy: women shop" is further explained for the fact that women invest in the overall shopping experience, while men are solely focused on the logistics of available parking, if the item is in stock, and how fast the interaction is. 

Code:
!pip install openai
from openai import OpenAI

client = OpenAI(
    api_key = "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",
)

completion = client.chat.completions.create(
    model="gpt-4",
    messages=[{"role": "user",
               "content": "do the shopping habits differ by gender and/or average age?"}],
    temperature=0
)
print(completion.choices[0].message.content)

Response:
Yes, shopping habits can significantly differ by both gender and average age. 

Gender: Men and women often have different shopping habits. For instance, women are generally more likely to enjoy the shopping process and take their time to browse, while men often prefer to quickly find what they need and leave. Women also tend to make more impulse purchases than men. In terms of product preferences, men often spend more on technology and gadgets, while women spend more on fashion and beauty products.

Age: Shopping habits also vary greatly by age. Younger consumers, for example, are more likely to shop online and make purchases through mobile devices. They are also more influenced by social media and peer reviews. Older consumers, on the other hand, may prefer shopping in physical stores and are more likely to stick to brands they know and trust. They may also value quality over price more than younger consumers.

However, these are general trends and individual shopping habits can vary greatly.


This response from GPT-4 aligns with my findings from the article by Knowledge at Wharton. However, the average age group among the overall shopping habits is younger than the dataset describes. Younger consumers tend to either enjoy a quick online shopping experience, while older consumers prefer physical stores and tend to be more loyal customers. My findings show that the average age group ranged from 40-47 years old. Aligning with the article as well, men tend to shop more in terms of value (purchase amount). 
