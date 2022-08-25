# Amazon Video Games Recommendation System
![Amazon video games](https://github.com/YueYu-95/Amazon-Recommendation-System/blob/main/Images/Amazon-Video-Games-Consoles-and-Devices-_-2018.jpg)

## Business Understanding 
In order to enhance the customer’s shopping experience, the online shopping sites usually have their own recommendation system to personalize each customer's shopping experience. Same as Amazon, as one of the biggest online retailers, Amazon has large number of products and variety of shopping categories. Hence, recommendation system becomes a powerful tool that can guide customers to the potential products they are looking for in a time saving way. Just like people who want to shop video games on Amazon, a good recommendation system could guide customers to their potentially interested games among thousands of products in a quick and easy way. Besides, Amazon’s variety of product categories can provide customers more than just games, but also accessories. For example, customers may also need a controller or headphone.  We could deploy the recommendation system at checkout page as a reminder and motive customers to purchase more. Hence, a great recommendation system could make Amazon to be a one-stop shop for every gamer.

## Data Overview
The data I used for the project is originally from Amazon.com and collected by department of computer science from UCSD. Due to the large size of the datasets, I’m not able to upload my data to this GitHub repository, but [here](https://nijianmo.github.io/amazon/index.html) is the link to access the data I used. The dataset contains 497,577 user reviews from May 1996 to Oct 2018 and each item have at least 5 reviews (5-core). Plus, a metadata includes descriptions, price, sales-rank, brand information of 84,819 video games/ accessories.

## Methods & Results
### Methods
For this project, I made three recommendation systems, trending products recommendations, content-based and collaborative filtering.
1. Trending Products Recommendations
First, a simple one which only recommends the trending products (top 10 most rated products). This method not only can show customers what are the current hot sale games and accessories, but also, most importantly, it solves cold start problem. 
Here is the screenshot of top 10 most rated products.
![trending product recommendations](https://github.com/YueYu-95/Amazon-Recommendation-System/blob/main/Images/trending_recom.PNG)
2. Content-Based
Next, the content-based recommendation system, it uses only information about the description and attributes of the items users have previously purchased or browsed to predict users' preferences. Here I checked the product’s category and brand. Then the recommendation system gives users suggestions on the products with the same category and brand.
Here is an example shows recommended product using content-based recommendation systems.
![content-based recommendations](https://github.com/YueYu-95/Amazon-Recommendation-System/blob/main/Images/content_based_recom.PNG)
3. Collaborative Filtering
Lastly, collaborative filtering, this method tries to predict the rating or preference that a user would give an item based on past ratings and preferences of other users. I used surprise python package to make the prediction. The algorithms I tried are NormalPredictor, BaselineOnly, KNN, SVD and SVDpp. The rmse was used as the metric to measure the performance of models.
![rmse comparison](https://github.com/YueYu-95/Amazon-Recommendation-System/blob/main/Images/RMSE%20Comparison.png)
The best model uses SVD algorithm and I was able to drop the rmse to 0.998.
Here is an example shows recommended product using the best model.
![collaborative filtering recommendations](https://github.com/YueYu-95/Amazon-Recommendation-System/blob/main/Images/collaborative_filtering_recom.PNG)
## Conclusion & Next Step
### Conclusion
In conclusion, trending products recommendation provides a good place to collect new users' information, so that we could avoid cold start problem. The content based method can filter out customers' potentially interested categories and brand. For the collaborative filtering, the best model is SVD has rmse 0.998, which is a significant drop comparing with baseline models. Generally speaking, all recommendation systems can provide accurate recommendations to specific users.
### Next Steps
- Deploy the recommendation system on the website
- Find a better data, that contains genres of games and more complete brand information.
- Do web scraping to get most updated data that includes latest video game consles, games and brands. (The current one only contains data from 1996-2018)
- Try the hybrid method.
- Run some AB tests on both new hybrid method and the best model I have.

# Repository Contents
- Data
- Images
- Pickle_Files
- .gitignore
- Amazon_Recommendation_System.ipynb
- LICENSE
- README.md
- presentaion.pdf
