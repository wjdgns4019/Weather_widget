# Weather_widget
(openweathermap - api)

```html
<div class="weather-widget" id="weather-widget">
</div>
<script>
  var apiURI = "https://local.ggm.pw/api/weather_api/Daegu.json";
  function displayWeather(resp) {
    var weatherWidget = document.getElementById('weather-widget');
    weatherWidget.innerHTML = `
      <h3>도시이름: ${resp.name}</h3>
      <h3>현재온도: ${Math.ceil(resp.main.temp)}℃</3>
      <h3>현재습도: ${resp.main.humidity} %</h3>
      <h3 class="weather-description">날씨: ${resp.weather[0].main} - ${resp.weather[0].description}</h3>
      <img src="https://local.ggm.pw/api/weather_icon/${resp.weather[0].icon}.png" alt="날씨 이미지" class="weather-icon"/>
      <p> </p>
      <h3>바람: ${resp.wind.speed} m/s</h3>
      <h3>구름: ${resp.clouds.all} %</h3>
    `;
  }

  $.ajax({
    url: apiURI,
    dataType: "json",
    type: "GET",
    async: "false",
    success: displayWeather
  })
  // ${resp.sys.country} KR 추가하고싶으면 넣어야함
</script>
<link rel="stylesheet" type="text/css" href="https://local.ggm.pw/api/weather_api/style.css">
```
