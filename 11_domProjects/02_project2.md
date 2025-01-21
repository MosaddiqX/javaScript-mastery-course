# 💻 Project 2: Weather App with API Integration

## 🎯 Description and Objectives

In this project, you will create a weather application that allows users to input their location (city name) and get current weather information. The app will use an external weather API to fetch data. You'll learn how to handle asynchronous operations, manipulate the DOM with fetched data, and handle API responses effectively.

## 📋 Steps to Complete Project 2

1. **Set up the basic HTML structure:**
   - Create a form to accept the city name as input.
   - Add a button to trigger the weather data fetch.
   - Display weather data such as temperature, humidity, and weather conditions dynamically.

2. **Fetching data from the API:**
   - Use `fetch()` to make a GET request to a weather API (e.g., OpenWeatherMap API).
   - Handle asynchronous operations using promises or async/await syntax.
   - Display the data in the DOM once the response is received.

3. **Handling errors:**
   - Add error handling for cases like invalid city names, no network, or API issues.
   - Show a user-friendly error message if something goes wrong (e.g., city not found or invalid API key).

4. **Enhance UI with dynamic updates:**
   - Add loading indicators while the weather data is being fetched.
   - Show a default message or placeholder until the weather data is available.
   - Style the app for a professional look (using CSS or Tailwind CSS).

5. **Adding extra features (optional):**
   - Allow users to switch between Celsius and Fahrenheit.
   - Save the last searched city in localStorage so that it remains even after page reloads.
   - Include additional weather information such as wind speed, UV index, and a forecast for the next 5 days.

---

## 🧑‍💻 Key Concepts and Techniques Applied

- **API Integration**: Learn how to fetch data from a third-party API (OpenWeatherMap or another weather API).
- **Async Programming**: Use promises or async/await to handle asynchronous operations.
- **DOM Manipulation**: Dynamically update the DOM based on the fetched data.
- **Error Handling**: Implement error handling for network issues and incorrect user inputs.
- **Local Storage**: Store data (such as the last searched city) in local storage to persist data across sessions.
- **CSS Styling**: Style the application to make it user-friendly and visually appealing.

---

## 📚 Example Code

```html
<!-- HTML Structure -->
<div id="app">
  <h1>Weather App</h1>
  <input type="text" id="cityInput" placeholder="Enter city name">
  <button id="getWeatherBtn">Get Weather</button>
  <div id="weatherInfo"></div>
  <div id="errorMessage"></div>
</div>

<script>
// JavaScript Code
const cityInput = document.getElementById('cityInput');
const getWeatherBtn = document.getElementById('getWeatherBtn');
const weatherInfo = document.getElementById('weatherInfo');
const errorMessage = document.getElementById('errorMessage');

// API Key from OpenWeatherMap
const apiKey = 'YOUR_API_KEY'; // Replace with your OpenWeatherMap API key

getWeatherBtn.addEventListener('click', function() {
  const cityName = cityInput.value;
  if (cityName) {
    getWeather(cityName);
  } else {
    errorMessage.textContent = 'Please enter a valid city name.';
    weatherInfo.innerHTML = '';
  }
});

async function getWeather(cityName) {
  try {
    const response = await fetch(`https://api.openweathermap.org/data/2.5/weather?q=${cityName}&appid=${apiKey}&units=metric`);
    const data = await response.json();

    if (data.cod === '404') {
      throw new Error('City not found');
    }

    const { main, weather } = data;
    weatherInfo.innerHTML = `
      <p>Temperature: ${main.temp}°C</p>
      <p>Humidity: ${main.humidity}%</p>
      <p>Weather: ${weather[0].description}</p>
    `;
    errorMessage.textContent = '';
  } catch (error) {
    errorMessage.textContent = error.message;
    weatherInfo.innerHTML = '';
  }
}
</script>
```

---

## ✅ Outcome

By the end of this project, you will have created a weather application that:
- Fetches and displays real-time weather data using an external API.
- Handles various errors (e.g., incorrect city name, network issues).
- Dynamically updates the UI with weather details such as temperature, humidity, and weather condition.
- Optionally stores the last searched city in localStorage and switches between temperature units.

---

## 📚 Resources

- [OpenWeatherMap API Documentation](https://openweathermap.org/api)
- [MDN - Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
- [MDN - Async/Await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)

---

### Instructions:
- Replace `YOUR_API_KEY` with your actual API key from OpenWeatherMap or another weather API provider.
