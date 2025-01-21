# 💻 Project 4: Movie Search App with External API Integration

## 🎯 Description and Objectives

In this project, you will create a **Movie Search Application** that fetches movie data from an external API (such as the OMDB API). The application will allow users to search for movies by title, view details about selected movies, and manage their search history.

Key features include:
- Search for movies by title
- Display movie details like title, year, poster, and plot
- Save and display previous search history
- Responsive UI design for mobile and desktop

## 📋 Steps to Complete Project 4

1. **Set up the project structure:**
   - Create a basic HTML, CSS, and JavaScript setup for the app.
   - Implement a simple UI with an input field for searching and an area to display the results.

2. **API Integration:**
   - Fetch movie data from the [OMDB API](http://www.omdbapi.com/).
   - Implement a search function that takes the movie title input from the user, sends it to the API, and displays the results.
   - Use `fetch()` or `axios` to handle the API requests and process the response data.

3. **Display Search Results:**
   - After fetching data from the API, display a list of movies with their title, year, and poster image.
   - Allow users to click on a movie title to view more details (e.g., full plot, rating, etc.).

4. **Search History:**
   - Keep track of the user's past searches and display a history of previously searched movie titles.
   - Allow users to click on a movie in the search history to see more details again.

5. **Responsive Design:**
   - Make the app responsive so that it works well on mobile and desktop devices.
   - Use media queries and flexible layouts to ensure the app looks good across different screen sizes.

6. **Error Handling and Validation:**
   - Handle errors when no movies are found or when the API request fails (e.g., incorrect API key or network issues).
   - Show appropriate messages to the user (e.g., "No results found" or "Please try again later").

---

## 🧑‍💻 Key Concepts and Techniques Applied

- **API Integration**: Learn how to make HTTP requests to external APIs and handle JSON responses.
- **DOM Manipulation**: Dynamically update the UI to display movie results and search history.
- **Local Storage**: Store search history persistently using `localStorage`.
- **Event Handling**: Use JavaScript to handle user interactions such as searching, clicking, and viewing movie details.
- **Responsive Design**: Apply CSS techniques to ensure the app is mobile-friendly and adapts to different screen sizes.

---

## 📚 Example Code

```html
<!-- HTML Structure -->
<div id="search-container">
  <h1>Movie Search</h1>
  <input type="text" id="search-input" placeholder="Enter movie title">
  <button id="search-btn">Search</button>
  <div id="movie-list"></div>
  <div id="movie-details" style="display:none;"></div>
  <h3>Search History</h3>
  <ul id="history-list"></ul>
</div>

<script>
// JavaScript Code
const apiKey = 'your-api-key'; // Replace with your OMDB API key
const searchButton = document.getElementById('search-btn');
const searchInput = document.getElementById('search-input');
const movieList = document.getElementById('movie-list');
const movieDetails = document.getElementById('movie-details');
const historyList = document.getElementById('history-list');

// Event listener for search button
searchButton.addEventListener('click', function() {
  const query = searchInput.value;
  if (query) {
    searchMovies(query);
    saveSearchHistory(query);
  }
});

// Function to search movies from the OMDB API
function searchMovies(query) {
  fetch(`https://www.omdbapi.com/?s=${query}&apikey=${apiKey}`)
    .then(response => response.json())
    .then(data => {
      if (data.Response === 'True') {
        displayMovies(data.Search);
      } else {
        movieList.innerHTML = 'No results found.';
      }
    })
    .catch(error => {
      movieList.innerHTML = 'Error fetching data. Please try again later.';
      console.error('Error:', error);
    });
}

// Function to display movie list
function displayMovies(movies) {
  movieList.innerHTML = '';
  movies.forEach(movie => {
    const div = document.createElement('div');
    div.className = 'movie-item';
    div.innerHTML = `
      <img src="${movie.Poster}" alt="${movie.Title}">
      <h3>${movie.Title} (${movie.Year})</h3>
      <button onclick="viewMovieDetails('${movie.imdbID}')">View Details</button>
    `;
    movieList.appendChild(div);
  });
}

// Function to view movie details
function viewMovieDetails(imdbID) {
  fetch(`https://www.omdbapi.com/?i=${imdbID}&apikey=${apiKey}`)
    .then(response => response.json())
    .then(data => {
      movieDetails.style.display = 'block';
      movieDetails.innerHTML = `
        <h2>${data.Title} (${data.Year})</h2>
        <img src="${data.Poster}" alt="${data.Title}">
        <p><strong>Plot:</strong> ${data.Plot}</p>
        <p><strong>Rating:</strong> ${data.imdbRating}</p>
        <button onclick="closeMovieDetails()">Close</button>
      `;
    });
}

// Function to close movie details
function closeMovieDetails() {
  movieDetails.style.display = 'none';
}

// Function to save search history
function saveSearchHistory(query) {
  let history = JSON.parse(localStorage.getItem('searchHistory')) || [];
  if (!history.includes(query)) {
    history.push(query);
    localStorage.setItem('searchHistory', JSON.stringify(history));
    displaySearchHistory();
  }
}

// Function to display search history
function displaySearchHistory() {
  let history = JSON.parse(localStorage.getItem('searchHistory')) || [];
  historyList.innerHTML = '';
  history.forEach(item => {
    const li = document.createElement('li');
    li.textContent = item;
    historyList.appendChild(li);
  });
}

// Load search history on page load
displaySearchHistory();
</script>
```

---

## ✅ Outcome

By the end of this project, you will have built a **Movie Search App** with the following features:
- **Movie Search**: Users can search for movies by title and view their details.
- **API Integration**: Fetch movie data from the OMDB API and display it in the app.
- **Search History**: Keep track of the user’s search history and allow them to click on past searches to view details.
- **Responsive Design**: Ensure the app works well on both mobile and desktop devices.
- **Error Handling**: Display appropriate messages if no results are found or if there is an issue with the API.

---

## 📚 Resources

- [OMDB API Documentation](http://www.omdbapi.com/)
- [MDN - Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
- [MDN - Local Storage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)

---

### Instructions:
- Replace the placeholder API key with your own OMDB API key.


