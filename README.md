## Mood-Based Recipe Recommender

This Python script utilizes machine learning and natural language processing to recommend recipes based on a user's mood input. It makes use of the `pandas`, `re`, `scikit-learn`, `numpy`, `ipywidgets`, and `IPython.display` libraries.

1. **Data Loading and Preprocessing:**
   - The code starts by importing the `pandas` library and loading a dataset of recipes from a CSV file named "recipes.csv".
   - A function called `clean_mood` is defined, which takes a mood input and removes any non-alphanumeric characters using regular expressions (`re.sub`). This cleaned mood is stored in a new column called "clean_mood" in the recipes DataFrame.

2. **Feature Extraction:**
   - The script imports the `TfidfVectorizer` class from `sklearn.feature_extraction.text`. This class converts text data into a matrix of TF-IDF features, which is a numerical representation suitable for machine learning.
   - An instance of `TfidfVectorizer` is created with the option to consider word unigrams and bigrams (ngram_range=(1,2)).
   - The `fit_transform` method is used to transform the cleaned mood data into a TF-IDF matrix.

3. **Similarity Calculation:**
   - The `cosine_similarity` function from `sklearn.metrics.pairwise` is imported. This function calculates the cosine similarity between vectors, which can be used to measure the similarity between moods and recipes.
   - The `numpy` library is imported to perform array operations.
   - A `search` function is defined, which takes a mood input, cleans it, converts it into a TF-IDF vector, calculates cosine similarity with existing recipes, and returns the top 5 most similar recipes.

4. **User Interface with Widgets:**
   - The code imports the `ipywidgets` library to create interactive widgets for user input.
   - A button widget is created with a description to enter a mood (e.g., "happy, sad, anxious...") and a text input widget for the user to type their mood.
   - An output widget is created to display the recommended recipes.

5. **Event Handling and Display:**
   - An event handler function named `on_type` is defined. It triggers when the user types a mood in the input widget.
   - The function clears the output area, cleans the mood input, performs a search for similar recipes, selects relevant columns from the results, and displays them.

6. **User Interaction:**
   - The `observe` method is used to link the mood input widget to the `on_type` function. When the user types a mood, the function is called to display relevant recipe recommendations.
   - The `display` function is used to show the button, mood input, and recommendation output widgets in the Jupyter Notebook interface.

This script offers an interactive way for users to input their mood and receive recipe recommendations based on the similarity of moods. It utilizes text processing and machine learning techniques to enhance the user experience in exploring recipes that match their emotional state.
