# End-to-End-Data-Science-Project
## Full Data Science Project: From Data Collection to Model Deployment
In this project, we will develop a complete data science pipeline, starting from data collection and preprocessing to model training and deployment using Flask or FastAPI. The final deliverable will be a deployed API or web app showcasing the model's functionality.

## Project Overview
We will build a House Price Prediction model using a dataset containing features of houses (e.g., square footage, number of bedrooms, location, etc.) and their corresponding prices. The model will be deployed as an API using Flask or FastAPI, allowing users to input house features and receive a predicted price.


## Step 1: Data Collection
We will use the California Housing Dataset from the sklearn.datasets module or a similar dataset from Kaggle (e.g., Kaggle House Prices Dataset).


## Step 2: Data Preprocessing
Handle Missing Values: Check for missing values and handle them (e.g., imputation or removal).

Feature Engineering: Create new features or transform existing ones (e.g., log transformation for skewed data).

Encoding Categorical Variables: Use one-hot encoding or label encoding for categorical features.

Scaling/Normalization: Scale numerical features to a standard range.


## Step 3: Model Training
We will use a Linear Regression model for simplicity, but you can experiment with more advanced models like Random Forest, Gradient Boosting, or Neural Networks.


## Step 4: Save the Model
Save the trained model and scaler using joblib or pickle for later use in the API.


## Step 5: Build the API with Flask
We will use Flask to create a simple API that accepts house features as input and returns the predicted price.

1.Install Flask:
                      
                         pip install flask
2.Create a Flask app:

3.Run the Flask app:

                         python app.py

4.Test the API using curl or Postman:

                      curl -X POST -H "Content-Type: application/json" -d '{"features": [1, 2, 3, 4, 5, 6, 7, 8]}' http://127.0.0.1:5000/predict


## Step 6: Deploy the API
You can deploy the Flask app using platforms like:

-Heroku

-AWS Elastic Beanstalk

-Google Cloud Run

-Render

For example, to deploy on Heroku:

1.Install the Heroku CLI and login.

2.Create a Procfile:

               web: python app.py

3.Push your code to Heroku:
                    heroku create
                    git push heroku main


## Step 7: Build a Web App (Optional)
You can create a simple web interface using HTML and JavaScript to interact with the API.

1.Create an index.html file

2.Serve the HTML file using Flask


## Deliverable
A deployed API or web app that allows users to input house features and receive a predicted price.

The API can be accessed via HTTP requests, and the web app provides a user-friendly interface.

## Next Steps
Improve the model by experimenting with different algorithms and hyperparameters.

Add more features to the dataset for better predictions.

Enhance the web app with additional functionality and styling.

This project demonstrates the end-to-end process of a data science workflow, from data collection to model deployment.


## Output
Here’s the expected output for each step of the code provided in the House Price Prediction project:

## Step 1: Data Collection
When you load the California Housing Dataset and display the first few rows, the output will look like this:

                  MedInc  HouseAge  AveRooms  AveBedrms  Population  AveOccup  Latitude  Longitude  MedHouseVal
              0  8.3252      41.0  6.984127   1.023810       322.0  2.555556     37.88    -122.23        4.526
              1  8.3014      21.0  6.238137   0.971880      2401.0  2.109842     37.86    -122.22        3.585
              2  7.2574      52.0  8.288136   1.073446       496.0  2.802260     37.85    -122.24        3.521
              3  5.6431      52.0  5.817352   1.073059       558.0  2.547945     37.85    -122.25        3.413
              4  3.8462      52.0  6.281853   1.081081       565.0  2.181467     37.85    -122.25        3.422


## Step 2: Data Preprocessing
After splitting the data into training and testing sets and scaling the features, you won’t see a direct output, but you can verify the shapes of the datasets:

           print(X_train.shape, X_test.shape, y_train.shape, y_test.shape)


Output:

            (16512, 8) (4128, 8) (16512,) (4128,)


## Step 3: Model Training
After training the Linear Regression model, you will evaluate it using Mean Squared Error (MSE). The output will look like this:

                Mean Squared Error: 0.5558915986952442


## Step 4: Save the Model
The model and scaler are saved to disk as house_price_model.pkl and scaler.pkl. No output is displayed, but you can verify the files are created in your working directory.

       
## Step 5: Build the API with Flask
When you run the Flask app, you will see the following output in the terminal:

              * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
              * Restarting with stat
              * Debugger is active!
              * Debugger PIN: 123-456-789


## Step 6: Test the API
When you test the API using curl or Postman, you will get a JSON response with the predicted house price. For example:

              curl -X POST -H "Content-Type: application/json" -d '{"features": [1, 2, 3, 4, 5, 6, 7, 8]}' http://127.0.0.1:5000/predict

Output:

               {
                     "predicted_price": 2.345
               }


## Step 7: Build a Web App (Optional)
When you open the web app in your browser (http://127.0.0.1:5000/), you will see a simple form where you can input house features. After submitting the form, the predicted price will be displayed below the form.

Example:

Input: 1, 2, 3, 4, 5, 6, 7, 8

Output: Predicted Price: 2.345


## Deployed API or Web App
Once deployed (e.g., on Heroku), the API or web app will be accessible via a public URL. For example:

*API: https://your-app-name.herokuapp.com/predict

*Web App: https://your-app-name.herokuapp.com/


## Summary of Outputs

Data Collection: Display the first few rows of the dataset.

Data Preprocessing: Verify the shapes of the training and testing datasets.

Model Training: Display the Mean Squared Error (MSE) of the model.

Save the Model: Verify the model and scaler files are saved.

Flask API: Run the Flask app and test the API using curl or Postman.

Web App: Interact with the web app and see the predicted price.

