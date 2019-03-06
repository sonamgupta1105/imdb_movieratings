# imdb_movieratings

The aim is to predict a movie’s average rating using datasets from the provided IMDB link. 
For this first round I have implemented multiple linear regression model.  
Dataset used: Basics, crew, and averageRating tsv files. 
Step 1: Data manipulation and cleaning
1.	Read the tsv files using pandas csv module and delimit by tab, and removed duplicates
2.	All the files have one column common and that is tconst which is an identifier
3.	Check for null values, replace the NaNs with 0 in numerical columns like averageRating and numVotes
4.	After summarizing the data, the noticeable content was that the data did not just have movies data but also some tv shows and short films. Thus, filtered the data to just be a subset of movies
Step 2: Data Preprocessing
Since there are text columns in the dataframe, basic processing was needed like changing the text case to lower case, replace some basic unnecessary punctuations and strip extra whitespace. 
Replace values like ‘\\N’ with blanks. Convert date and averageRating columns to float type.
Step 3: Data Visualization
Since linear regression model is built, the assumption of linearity between the dependent variable (averageRating) and predictor numerical variables like numVotes and runtimeMinutes, was identified by plotting scatter plots. 
From the plot between averageRating and numVotes, show a non-linear, positive but weak association between these variables whereas the other plot showed no linearity at all. 
To understand the correlation between other numerical variables, a heatmap was created. The values of correlation closer to 0 , showed no linear relation while values closer to 1 indicated strong relationship.
Step 4: Building multiple linear regression model
For linear regression model, three variables were considered for X labels: startYear, numVotes, and genres whereas Y is averageRating. 
Since genres has three types of values, we can encode it to vectorize to use it well in the linear regression model. 
From the training results, we understand that the model did not perform too well with small coefficient of 0.0016 increase in average rating associated with just a tad bit increase in succeeding years, different genres and number of votes. 
Step 5: Evaluation of model
With a value of RMSE = 2.852, there are chances for more improvement in the model with better suited variables. 
