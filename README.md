# webtest
웹프로그래밍 git 원격저장

제가 만들 기말프로젝트는 날씨를 알려주는 웹사이트입니다.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>오늘의 날씨</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>오늘의 날씨</h1>
    <nav>
        <ul>
            <li><a href="#weather">오늘의 날씨</a></li>
            <li><a href="#forecast">7일간의 일기예보</a></li>
            <li><a href="#about">About</a></li>
        </ul>
    </nav>
    <div class="content">
        <section id="weather">
            <h2>오늘의 날씨</h2>
            <div class="weather-info">
                <h3>Temperature: <span id="temperature"></span></h3>
                <h3>Condition: <span id="condition"></span></h3>
            </div>
        </section>

        <section id="forecast">
            <h2>7일간의 일기예보</h2>
            <div id="forecastInfo"></div>
        </section>

        <section id="about">
            <h2>오늘의 날씨에 대하여</h2>
            <p>이 웹사이트는 오늘의 날씨에 대하여 알려주는 사이트입니다.</p>
        </section>
    </div>

    <script src="script.js"></script>
</body>
</html>
스타일 CSS 코드 
body {
    font-family: Arial, sans-serif;
    background-color: #0000FF;
}

h1 {
    color: #333;
    text-align: center;
}

nav ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    text-align: center;
}

nav ul li {
    display: inline-block;
    margin: 0 10px;
}

nav ul li a {
    text-decoration: none;
    color: #yellow;
}

.content {
    margin: 20px;
    background-color: #blue;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

section {
    margin-bottom: 40px;
}

.weather-info {
    display: flex;
    justify-content: center;
    align-items: center;
}

.weather-info h3 {
    margin: 0 10px;
}

#temperature {
    font-size: 24px;
    transition: font-size 0.3s ease-in-out;
}

#condition {
    font-size: 18px;
}

#temperature:hover {
    font-size: 30px;
}

#temperature.rotate {
    transform: rotate(45deg);
}

a:hover {
    color: #ff0000;
}

section:not(:last-child) {
    position: relative;
    margin-bottom: 80px;
}

section:not(:last-child):after {
    content: "";
    position: absolute;
    bottom: -60px;
    left: 50%;
    transform: translateX(-50%);
    width: 80px;
    height: 3px;
    background-color: #333;
}

자바스크립트 코드 
window.addEventListener("load", function() {
    // Function to get the current weather information
    function getWeather() {
        // Replace the following lines with your own logic to fetch the weather data
        var weatherData = {
            temperature: "25°C",
            condition: "Sunny"
        };

        return weatherData;
    }

    // Function to display the weather information
    function displayWeather() {
        var temperatureElement = document.getElementById("temperature");
        var conditionElement = document.getElementById("condition");

        var weatherData = getWeather();

        temperatureElement.innerText = weatherData.temperature;
        conditionElement.innerText = weatherData.condition;
    }

    // Function to handle temperature element events
    function handleTemperatureEvents() {
        var temperatureElement = document.getElementById("temperature");

        temperatureElement.addEventListener("mouseenter", function() {
            this.classList.add("rotate");
        });

        temperatureElement.addEventListener("mouseleave", function() {
            this.classList.remove("rotate");
        });
    }

    displayWeather();
    handleTemperatureEvents();
});
