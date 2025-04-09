# Content-Based Movie Recommender System

![Screenshot from 2025-02-13 03-24-29](https://github.com/user-attachments/assets/8fe18ea6-2fd4-4177-991f-81c9724ca54f)

This is a content-based movie recommender system built using a dataset of 5000 movies. The system recommends movies based on a given movie title by analyzing the content (overview, genre, keywords, cast, and crew) of the movies. The project is divided into four main parts: data preprocessing, model building, website building, and deployment.


## Features
- Recommends top 10 similar movies based on the selected movie title.
- Uses content-based filtering based on movie attributes like genre, cast, crew, overview, and keywords.
- Displays movie posters for the recommended movies using The Movie Database (TMDb) API.
- Built using Streamlit for an interactive and user-friendly interface.

## Project Structure
The project is divided into the following steps:
1. **Data Preprocessing**: Clean and prepare the movie dataset for model training.
2. **Model Building**: Train the recommendation system using cosine similarity on the movie's content-based features.
3. **Website Building**: Build an interactive web application using Streamlit to allow users to interact with the recommendation system.
4. **Deployment**: Deploy the web app on Streamlit and make it publicly accessible.

## Technologies Used
- **Machine Learning**: Python, scikit-learn
- **Web Framework**: Streamlit
- **API Integration**: The Movie Database (TMDb) API
- **Data Handling**: pandas, numpy
- **Version Control**: Git, GitHub

## Data Preprocessing
The dataset contains 5000 movies and 20 columns. The preprocessing steps focused on retaining the key features that influence movie recommendations:
- Removed irrelevant columns such as budget, revenue, popularity, and runtime.
- Retained important columns: `movie_id`, `title`, `overview`, `genre`, `keywords`, `cast`, and `crew`.
- Applied functions to extract the top 3 cast members and the director's name from the respective columns.
- Concatenated the `overview`, `genres`, `keywords`, `cast`, and `crew` into a new column `tags`, which served as the input for the recommendation model.
  
The final dataset was reduced to only `movie_id`, `title`, and `tags`.

## Model Building
The recommendation system uses content-based filtering with cosine similarity:
1. **Vectorization**: I used `CountVectorizer` to convert the tags column into a matrix of token counts.
2. **Cosine Similarity**: Calculated the cosine similarity between movies based on their tags.
3. **Recommendation Function**: A function was created that takes a movie title as input, finds the most similar movies based on cosine similarity, and returns the top 10 recommendations.

The movie recommendations are sorted based on their similarity score.

## Website Building (Streamlit)
The website was built using **Streamlit** to allow users to input a movie title and receive movie recommendations.
1. **Dropdown Menu**: Users can select a movie from a dropdown populated with movie titles.
2. **Recommendation Button**: Once a movie is selected, clicking the "Recommend" button generates the top 10 similar movies.
3. **Movie Posters**: The TMDb API is used to fetch movie posters, and the recommended movies are displayed along with their posters in a visually appealing layout.



## Live Application

You can try the live version of the application here: [Live Demo](https://movie-recommender-system-dswnatcgskkyqjve7m9shk.streamlit.app/)

## How to Run the Project Locally

### Prerequisites
- Python 3.8+
- Streamlit
- pandas, numpy, scikit-learn
- The Movie Database (TMDb) API key

### Installation Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/movie-recommender.git
   cd movie-recommender
   pip install -r requirements.txt
   streamlit run app.py



