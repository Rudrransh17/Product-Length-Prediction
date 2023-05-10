# Product Length Prediction

This is a project that aims to predict the length of a product based on its name, description, and features. The project uses TF-IDF encoding to preprocess the data into vectors, and a Keras Sequential neural network model to train and predict the length of the products.

## Data

The project uses a dataset of various products with their name, description, bullet points, product type ID, and product length. The `train.csv` file contains the training data, and the `test.csv` file contains the testing data. Both files consist of the following columns:

- `PRODUCT_ID`: The ID of the product.
- `TITLE`: The title of the product.
- `BULLET_POINTS`: The bullet points of the product.
- `DESCRIPTION`: The description of the product.
- `PRODUCT_TYPE_ID`: The type of the product.
- `PRODUCT LENGTH`: The length of the product (available only in the `train.csv` file).

The data consisting of title, bullet points, and description was first tokenized and then transformed into a TF-IDF vector of size 250.

## Model

The project uses a Keras Sequential neural network model to predict the length of the products. The model consists of six layers:

- 3 dense layers with 2048 units, ReLU activation function, batch normalization, and dropout of 0.3.
- 3 dense layers with 1024 units, ReLU activation function, batch normalization, and dropout of 0.3.

The model was trained on the preprocessed dataset using the Mean Absolute Percentage Error (MAPE) loss function and the Adam optimizer. Validation was done using MAPE as well, and an early stopping callback was used to prevent overfitting. 


## Usage

To run the project, you need to have Python 3 installed, along with the following libraries:

- pandas
- nltk
- scikit-learn
- tensorflow

To predict the length of a product, you need to provide its title, bullet points, and description in a CSV file with the following format:

```
TITLE,BULLET_POINTS,DESCRIPTION
product_title,product_bullet_points,product_description
```

## Conclusion

This project demonstrates how to use TF-IDF encoding and a Keras Sequential neural network model to predict the length of products based on their title, bullet points, and description. The project achieved a high accuracy on the testing data using MAPE as the evaluation metric, and an early stopping callback to prevent overfitting. The project can be easily adapted to other similar prediction tasks.
