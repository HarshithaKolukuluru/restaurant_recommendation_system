# Restaurant Recommendation System
## Motivation and About the Project
Recommendation engines are systems that
make recommendations tailored to fit a user's
preferences and thereby improve user
experience.

In this project, we aim to build a
recommendation system that recommends
restaurants with the Yelp academic dataset.

## Data and Labels
Converted the available code: json_to_csv
converter on Yelp's GitHub from python2 to
python3 to convert our dataset.

The restaurant data was merged with the user
data to give a total of more than 4 million data
points. It had to be reduced to around a million
consisting of data from only the restaurants that
have more than 50 reviews.

## Model
For training our model, we split our data into training, validation, and
test sets based on when the rating was given, the most recent ratings
are held out, the second most were used in the validation set and the
rest in the training set. The model was then trained with SGD
optimizer with MSE as its loss function. 

The following functions were used to recommend a restaurant to the user:

1. **predict_ratings:** takes the userid as an input and predicts the
ratings for all the restaurants which are not rated by that user.
2. **recommend_restaurants:** takes the userid as the input and
recommends restaurants based on predicted ratings.
3. **recommend_based_on_friends:** this calculates the average
rating of all the friends of a user on the restaurants they have
rated and will recommend restaurants to a user based on that
average ratings.
4. **recommend_based_on_location:** this will simply recommend the user the restaurants using the above functions but also takes a user’s current location into consideration.
(Only recommends those restaurants which are located in users current location)

## Results

After performing some EDA, we see that the largest number of
reviewed are from Toronto, Ohio. Las Vegas, Nevada has the most
top-rated restaurants. Bacchanal Buffet, Las Vegas is the most
reviewed restaurant. Earl of Sandwich, Las Vegas is the best
restaurant on the basis of review counts and ratings. The restaurant
with the most number of storefronts is McDonald's. most reviewed
restaurant among the biggest chain restaurants is McDonald's.
Despite being the most rated, McDonald's has an average rating of
1.9 stars only which appears to be the case for other big restaurant
chains as well.

## Conclusion and Future Work
### Conclusion:
We found the model to have a MSE of
2.9 which is not satisfactory. This can
be improved with hyperparameter
tuning and using more data for
training in the future.
We also trained the model using the
Adam optimizer and 2M data points
for training and got an MSE of 1.77,
which is proved to be an improvement
over the previous model one.

### Future Work:
The ratings for SGD can be improved
by using geo-location, attributes such
as vegan, alcohol etc which further
narrow down the preference and
hence improve the predicted rating of
the user. A comparison with user-user,
item-item and user-item can help
further analyse why our MSE from
SGD and Adam is low.

## References

https://github.com/mustafashabbir10/Yelp-Recommender-System/blob/master/Recommender_System.ipynb

## Libraries Used
Pandas | NumPy | Matplotlib | Seaborn | Plotly | Cartopy | TensorFlow | Keras
