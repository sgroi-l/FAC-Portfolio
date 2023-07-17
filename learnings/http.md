## 1. Write code that executes asynchronously

```javascript
fetch(`https://api.openweathermap.org/data/2.5/weather?q=${input}&appid=62f3a1ae06706d5807a4f7d172197411`,{
    method: 'GET',
    headers: {
      'Accept': 'application/json'
    }
  })
  .then((response) => {
    if (!response.ok) {
      throw new Error(response.status);
    }
    return response.json();
  })
```

## 2. Use callbacks to access values that aren’t available synchronously

```javascript
export function getHistory(dataHistoryElement) {
let weatherHistory = JSON.parse(window.localStorage.getItem("weatherDetails"));
let activityHistory = window.localStorage.getItem("activityDetails");

weatherHistory.forEach(element => {
    const temperatureElement = createElement("h1", "temperature", `${element.temperature}\u00B0C`);
    const locationElement = createElement("p", "location", `${element.locationName}, ${element.locationCountry}`);
    const dateElement = createElement("p", "date", element.date);
    
    dataHistoryElement.append(temperatureElement, locationElement, dateElement);
});
}
```
## 3 & 4 Use promises to access values that aren’t available synchronously, Use the fetch method to make HTTP requests and receive responses

```javascript
fetch(`https://www.boredapi.com/api/activity?type=${randomType}`)
      .then((response) => {
        if (!response.ok) {
          throw new Error(response.status);
        }
        return response.json();
      })
      .then((jsonData) => {
        // Create element
        const activityElement = createElement('h2', 'activity', `Try a ${jsonData.type} activity today. ${jsonData.activity}.`);
        renderElement.append(activityElement);
```


## 5. Configure the options argument of the fetch method to make GET requests 

See 1.

## 6. Use the filter array method to create a new array with certain values removed

```javascript
// Remove the selected type from the typeArray
        const filteredArray = typeArray.filter(type => type !== randomType);
        typeArray = filteredArray.length > 0 ? filteredArray : (temperature >= 20 ? ["social", "recreational", "charity"] : ["education", "cooking", "relaxation"]);
```

## 7. Access DOM nodes using selector

```javascript
let dataHistoryElement = document.querySelector("#data-history");
```

## 9. Add and remove DOM nodes to change the content on the page

```javascript
// Function to render weather data to the page
export function renderWeatherData(temperature, name, country, renderElement) {
    const temperatureElement = createElement("h1", "temperature", `${temperature}\u00B0C`);
    const locationElement = createElement("p", "location", `${name}, ${country}`);
    renderElement.append(temperatureElement, locationElement);
  }
```


## 11. Use consistent layout and spacing

## 12. Follow a spacing guideline to give our app a consistent feel

## 13. Debug client side JS in our web browser

## 14. Use console.log() to help us debug our code
