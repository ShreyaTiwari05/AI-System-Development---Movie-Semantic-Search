# 🎬 Movie Semantic Search System

This project implements a semantic search system for movie plots. It leverages the `SentenceTransformers` library, specifically the **`all-MiniLM-L6-v2`** model, to generate vector embeddings from movie plot summaries and perform similarity-based searches.

---

## 🚀 Setup and Installation

Follow these steps to get the project up and running on your local machine.

1.  **Clone the Repository**
    ```bash
    git clone [https://github.com/your-username/AI-System-Development---Movie-Semantic-Search.git](https://github.com/your-username/AI-System-Development---Movie-Semantic-Search.git)
    cd AI-System-Development---Movie-Semantic-Search
    ```

2.  **Create and Activate a Virtual Environment**
    It's recommended to use a virtual environment to manage project dependencies.
    ```bash
    # Create the virtual environment
    python -m venv venv

    # Activate on Windows
    venv\Scripts\activate

    # Activate on macOS/Linux
    source venv/bin/activate
    ```

3.  **Install Dependencies**
    Install all the required packages using the `requirements.txt` file.
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the Jupyter Notebook**
    The main solution and demonstration are available in the notebook.
    ```bash
    jupyter notebook movie_search_solution.ipynb
    ```

---

## 🛠️ Usage

You can use the search functionality either as a Python module or directly from the command line.

### As a Python Module

Here is an example of how to import and use the search functions in your own Python script.

```python
from movie_search import load_movies, build_encoder, compute_embeddings, search_movies

# Load the movie dataset
df = load_movies("movies.csv")

# Build the encoder model
model = build_encoder()

# Compute embeddings for the movie plots
embeddings = compute_embeddings(model, df["plot"])

# Perform a search
query = "a spy thriller that takes place in Paris"
results = search_movies(query, top_n=5, model=model, df=df, embeddings=embeddings)

print(results)
````

### From the Command Line

You can also run a search directly from your terminal.

```bash
python movie_search.py --csv movies.csv --query "a spy thriller that takes place in Paris" --top-n 5
```

-----

## ✅ Running Tests

Unit tests are included to verify the system's functionality. To run them, execute the following command from the project's root directory:

```bash
python -m unittest tests/test_movie_search.py -v
```

### Test Results

All tests pass successfully.

\<details\>
\<summary\>Click to view full test output\</summary\>

```
============================= test session starts =============================
platform win32 -- Python 3.11.0, pytest-8.4.1, pluggy-1.6.0
rootdir: C:\ai\1\movie-search-assignment
collected 4 items

tests/test_movie_search.py::TestMovieSearch::test_search_movies_output_format PASSED [ 25%]
tests/test_movie_search.py::TestMovieSearch::test_search_movies_relevance PASSED [ 50%]
tests/test_movie_search.py::TestMovieSearch::test_search_movies_similarity_range PASSED [ 75%]
tests/test_movie_search.py::TestMovieSearch::test_search_movies_top_n PASSED [100%]

============================== 4 passed in ...s ===============================
```

\</details\>

```
```
