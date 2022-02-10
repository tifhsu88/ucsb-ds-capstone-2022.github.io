# Update 1 - Project Updates #

## Introduction: ##

Appfolio is a tech company based in Santa Barbara that provides innovative software, services, and data analytics to the real estate industry.  They specialize in being “100% Customer Focused” with services that fit the needs of different types of businesses. Their most popular and successful platform is their Property Management service, which we are currently working with.

## About the Project ##

The main purpose of this project is to create an app that recommends properties to users based on their interest clusters. In addition some of the goals that the team is focusing on are recommending properties to new customers and this can be done through capturing customer’s interests from data and generating predictions, analyzing inputs by data and ML algorithms, obtaining inputs from a new user and this can be done through search history or onboarding questions.

We think our work on this project would benefit Appfolio since this project is driven by how their users interact on their management platform to properties. It will be useful for them to see our results from our recommender system to see the usefulness of interaction data to better their products.

## About the Data ##

Our dataset is derived from a LISA AI chatbot that divides the data into three components: user ratings, item features, and images.

In our ratings data, we have a unique identifier for the property and the user along with the leasing attribution source and the type of interaction. The interaction type can be one of four scenarios; a user can deny a property, inquire about a property, accept a showing for a property, or confirm the showing by making an appearance. We use these interaction types as our response variable to gauge levels of interest in user-property pairs.

Our “item features” dataset is linked to the user matrix by the user ID. Within this set, we are given 15 unique features that comprise the makeup of a property and can be used to distinguish from other properties. An example of some of these features include property type (single family residence vs. multiple family residence), the number of rentable units, the date that it appears on the market, and the latitude and longitude.

The final partition of the data is the set of images that correspond to the properties within the other two segments of the data.


## What have we done so far ##

Currently working in teams to clean the data and test out different recommender system models. 

For the data cleaning, we’ve communicated with the sponsor about what the different attributes in the data represent and how it can add as a feature in our model. We’ve changed the current INTERACTION_TYPE, or ratings to numbers so they can be used in the Experimental Library we are using. In addition, will will begin experimenting different rating ranges soon (i.e. using 1-4 or 0-3). 

For the Model Testing, we’ve taken the time to understand the libraries and recommender system concepts that we will be using. Our models are tested using Cornac which makes it easier to test and experiment with multiple different multimodal recommender systems. In addition, this team is focused on applying the BiLateral Variational Autoencoder recommender system to our final project. Right now, we are building a simple model with a smaller dataset with no images. 

We are currently meeting weekly with Appfolio’s CS Capstone to help them with their current recommendations on their website.

## Obstacles ##

### Data Struggles

Our data consisted of uninformative labels and unintuitive names for values which gave us questions to research and ask our sponsors about . We created a documentation page for our entire dataset so we can use it for quick reference and help future collaborators understand our data. The “item features” dataset includes many null observations which we are unsure on how best to deal with. Our options include dropping the observations that include null values and increasing our precision on the data that we do include, but we would miss out on valuable information regarding recommending the properties we left out. Our other option is to find a way to work around the null observations and perhaps figure out a way to derive default values for these observations.

### Model Complexity

![](https://cdn.discordapp.com/attachments/927701734791458819/938995959747198986/Screen_Shot_2022-01-27_at_7.27.47_PM.png)

It has been a learning curve to understand how recommender systems work. Our chosen model consists of four encoders and one decoder to make item recommendations. It has been a puzzle deciphering the research paper for our model and getting it working to train. Lots of data and a complex model makes training time increase tremendously. It currently takes over thirty minutes for one epoch and our model needs a considerable amount of epochs to be accurate. We talked with our sponsors and set up a notebook on Google cloud that enables us to use GPUs to train more efficiently.


## Future Tasks ##

1. Continue learning about the Bilateral Variational Autoencoder
2. Clean the larger dataset that includes the properties of the CS capstone team’s database
3. Consider other ways to deal with missing data without removing it
4. Find default values in replacement with missing data
5. Update our model to suit the CS team capstone’s website
6. Figure out a way to map between our dataset and the CS capstone team’s dataset
7. Implement our prediction model to the CS capstone team’s website (see image of CS team’s website below)

![](https://cdn.discordapp.com/attachments/927701734791458819/938995930642915408/Screen_Shot_2022-02-03_at_6.10.44_PM.png)

For next quarter:

Upgrade our model with complex features including:

- Images

- Latitude and longitude of property

