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

## 8. Add and remove DOM nodes to change the content on the page

```javascript
// Function to render weather data to the page
export function renderWeatherData(temperature, name, country, renderElement) {
    const temperatureElement = createElement("h1", "temperature", `${temperature}\u00B0C`);
    const locationElement = createElement("p", "location", `${name}, ${country}`);
    renderElement.append(temperatureElement, locationElement);
  }
```


## 9. Use consistent layout and spacing

## 10. Follow a spacing guideline to give our app a consistent feel

Consistent use of gaps and padding around UI elements ensures that there is enough space between elements, making the app's layout more balanced and less cluttered. You can see here how I preset gap sizes within the `:root` element

```css
:root {
    font-size: 10px;
    font-family: 'Source Sans 3', sans-serif;
    font-weight: 400;
    --primary-color: #FFFBF3;
    --second-color: #deb65ed4;
    --small-font: 1.25rem;
    --medium-font: 1.75rem;
    --large-font: 3rem;
    --small-gap: 1rem;
    --medium-gap: 2rem;
    --large-gap: 3rem;
  }
```

## 11. Debug client side JS in our web browser

I faced an issue with activity repetition. I stored activity types in an array and used `pop()` to remove a selected type, but it wasn't working as expected.

 I added console logs to track the state of the array after each activity selection and removal. By triggering the event that called the `handleFormSubmit` function, I observed the console logs in the browser's developer tools. Based on the console output, I realised the filtering logic in the second fetch call was not updating the array correctly. I revised the filtering logic to properly remove the selected activity type from the array. After making the changes, I tested the application again and confirmed that the array was now being updated correctly, and the activity suggestions were no longer repeating. Once the issue was resolved, I removed the console logs to clean up the code. Debugging with console logs allowed me to quickly pinpoint the problem and make necessary adjustments for the desired behavior in activity selection.


