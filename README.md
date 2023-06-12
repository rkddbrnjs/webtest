# webtest
웹프로그래밍 git 원격저장

제가 만들 기말프로젝트는 맛집 검색 홈페이지입니다. 원하는 지역과 음식을 검색하면 네이버에 검색이 됩니다.
<!DOCTYPE html>
<html>
<head>
  <title>맛집을 찾으시나요?</title>
  <style>

    body {
      font-family: Arial, sans-serif;
      background-color: #00FF00;
      margin: 0;
      padding: 0;
    }

    header {
      background-color: #333;
      color: #fff;
      padding: 20px;
      text-align: center;
    }

    main {
      max-width: 800px;
      margin: 20px auto;
      padding: 20px;
      background-color: #fff;
      box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
    }

    input[type="text"] {
      width: 100%;
      padding: 10px;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 4px;
      margin-bottom: 10px;
    }

    button {
      padding: 10px 20px;
      font-size: 16px;
      background-color: #333;
      color: #fff;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }

    button:hover {
      background-color: #555;
    }

    .results {
      margin-top: 20px;
    }

    .result-item {
      padding: 10px;
      border-bottom: 1px solid #ccc;
    }
  </style>
</head>
<body>
  <header>
    <h1>맛집을 찾으시나요?</h1>
  </header>
  <main>
    <input type="text" id="food-input" placeholder="어떤 음식을 찾으시나요?">
    <input type="text" id="location-input" placeholder="어떤 지역에서 찾으시나요?">
    <button id="search-button">검색</button>
    <div class="results">
    </div>
  </main>

  <script>

    const searchButton = document.getElementById('search-button');
    const resultsContainer = document.querySelector('.results');

    searchButton.addEventListener('click', performSearch);

    function performSearch() {
      const foodQuery = document.getElementById('food-input').value;
      const locationQuery = document.getElementById('location-input').value;

      const searchUrl = `https://search.naver.com/search.naver?query=${foodQuery} ${locationQuery}`;
      window.open(searchUrl);
    }
  </script>
</body>
</html>
