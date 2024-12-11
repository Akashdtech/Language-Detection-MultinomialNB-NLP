# Language-Detection-MultinomialNB-NLP
This project implements a language detection model using machine learning techniques. Here's a breakdown of the steps:

Data Loading and Exploration:

    The dataset is loaded from a CSV file using pandas.
    The shape and unique values of the Language column are examined to understand the dataset's structure and distribution.

Text Preprocessing:

    CountVectorizer: This converts the text into a sparse matrix of word counts, representing how often each word appears in the text.
    TfidfVectorizer: This also converts text into a matrix, but it adjusts the word counts based on their importance in the text, accounting for the frequency of words across all documents.
    Both transformations are applied to the text data, and their results are combined using hstack (horizontal stack) into a single feature set.

Model Building:

    Multinomial Naive Bayes (MultinomialNB): This classification algorithm is commonly used for text classification problems. It assumes that the features (word counts or TF-IDF values) are conditionally independent given the class, and it is particularly effective for sparse data like text.
    The model is trained on the training dataset (X_train, y_train).

Model Evaluation:

    The model is evaluated using the test dataset (X_test, y_test), and the accuracy score is printed.
    The classification_report gives a detailed report with metrics like precision, recall, and F1-score for each language class.

Real-time Language Detection:

    The model allows the user to input a sentence to detect the language. The input text undergoes the same preprocessing (count vectorization and TF-IDF transformation) as the training data.
    The model then predicts the language of the input text and prints the result.

Key Features:

    Text Transformation: Both CountVectorizer and TfidfVectorizer are used together to capture both the frequency of words and their importance.
    Multinomial Naive Bayes: This classifier is suitable for multi-class classification tasks like language detection.

Example Output:

If you run this code with an input like "Hola, ¿cómo estás?", the model will predict the language as Spanish.
