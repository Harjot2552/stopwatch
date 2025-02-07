# Stopwatch

## Description
A simple and functional stopwatch application built using HTML, CSS, and JavaScript. The stopwatch allows users to start, stop, and reset the timer, displaying hours, minutes, and seconds.

## Features
- ⏱️ Start the stopwatch with a click.
- 🛑 Stop the stopwatch without resetting.
- 🔄 Reset the stopwatch to `00:00:00`.

## Demo
Link - https://harjotrocks.com/javascript/stopwatch/

## Technologies Used
- **📝 HTML**: Structure of the application.
- **🎨 CSS**: Styling and layout.
- **🤖 JavaScript**: Logic for time tracking and button interactions.

## How to Use
1. 📂 Clone the repository or download the files.
2. 🗃️ Open `index.html` in a web browser.
3. ⏯️ Click the **Start** button to begin the timer.
4. 🛑 Click the **Stop** button to pause the timer.
5. 🔄 Click the **Reset** button to reset the stopwatch.

## Code Explanation
### 📚 HTML
The HTML structure defines the layout of the stopwatch application, including:
- **Time Display:** A `<h1>` element (`id="displayTime"`) to display the current stopwatch time.
- **Buttons:** Three images acting as buttons for start, stop, and reset functionalities.

### 🎨 CSS
Basic CSS is used to style and position elements within the stopwatch interface, giving a clean and user-friendly layout.

### 💻 JavaScript
#### Variables:
- `seconds`, `minutes`, `hours`: Variables to keep track of the elapsed time.
- `displayTime`: Reference to the HTML element displaying the stopwatch time.
- `timer`: Stores the timer interval object.

#### Functions:
```javascript
function stopwatch() {
    seconds++;
    if (seconds == 60) {
        seconds = 0;
        minutes++;
        if (minutes == 60) {
            minutes = 0;
            hours++;
        }
    }
    let h = hours < 10 ? "0" + hours : hours;
    let m = minutes < 10 ? "0" + minutes : minutes;
    let s = seconds < 10 ? "0" + seconds : seconds;
    displayTime.innerHTML = h + " : " + m + " : " + s;
}
```
- **`stopwatch()`:** Increments time and updates the display every second.
  - Resets seconds when they reach 60.
  - Resets minutes when they reach 60 and increments hours.
  - Formats time values to always show two digits.

```javascript
function watchStart() {
    if (timer != null) {
        clearInterval(timer);
    }
    timer = setInterval(stopwatch, 1000);
}
```
- **`watchStart()`:** Starts the timer by setting a recurring call to `stopwatch()` every second.

```javascript
function watchStop() {
    clearInterval(timer);
}
```
- **`watchStop()`:** Stops the timer by clearing the interval.

```javascript
function watchReset() {
    clearInterval(timer);
    [seconds, minutes, hours] = [0, 0, 0];
    displayTime.innerHTML = "00 : 00 : 00";
}
```
- **`watchReset()`:** Resets the time values to zero and updates the display accordingly.


## Improvements
- 🌟 Enhance the UI/UX with better styling.
- 🔔 Add optional sound effects for start/stop/reset.
- ⏲️ Implement lap time functionality.


