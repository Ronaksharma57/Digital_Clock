
# Digital Clock

This is a simple digital clock that displays the current time in hours, minutes, seconds, and AM/PM.
# Hosted Link: 
https://ronaksharma57.github.io/Digital_Clock/

## How to use

To use this clock, simply open the `index.html` file in a web browser. The clock will start running automatically.

## Code

The code for this clock is very simple. The HTML file contains the basic structure of the clock, and the CSS file styles the clock. The JavaScript file contains the code that makes the clock run.

### HTML

The HTML file contains the following code:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Digital_Clock</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <h2>Digital Clock</h2>
    <div class="clock">
      <div>
        <span id="hour">00</span>
        <span class="text">Hours</span>
      </div>
      <div>
        <span id="minutes">00</span>
        <span class="text">Minutes</span>
      </div>
      <div>
        <span id="seconds">00</span>
        <span class="text">Seconds</span>
      </div>
      <div>
        <span id="ampm">AM</span>
      </div>
    </div>
    <script src="index.js"></script>
  </body>
</html>
```

The HTML code creates the basic structure of the clock. The `<h2>` tag creates the title of the clock, and the `.clock` div contains the clock itself. The `.clock` div is divided into four divs, one for each part of the clock (hours, minutes, seconds, and AM/PM). Each div contains a `span` tag with the ID of the corresponding part of the clock. The `span` tags will be used to display the time.

### CSS

The CSS file contains the following code:

```
body {
    margin: 0;
    font-family: sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100vh;
    justify-content: center;
    background-size: cover;
    background-image: url("https://images.unsplash.com/photo-1575203091586-611fe505bb0e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxleHBsb3JlLWZlZWR8NHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=600&q=60");
    overflow: hidden;
  }
  
  h2 {
    text-transform: uppercase;
    letter-spacing: 4px;
    font-size: 14px;
    text-align: center;
    color: white;
  }
  
  .clock {
    display: flex;
  }
  
  .clock div {
    margin: 5px;
    position: relative;
  }
  
  .clock span {
    width: 100px;
    height: 80px;
    background: slateblue;
    opacity: 0.8;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 50px;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
  }
  
  .clock .text {
    height: 30px;
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 2px;
    background: darkblue;
    opacity: 0.8;
  }
  
  .clock #ampm {
    bottom: 0;
    position: absolute;
    width: 60px;
    height: 30px;
    font-size: 20px;
    background: green;
  }
```### JS

The JS file contains the following code:
```
const hour = document.getElementById("hour");
const minute = document.getElementById("minutes");
const second = document.getElementById("seconds");
const ampm = document.getElementById("ampm");

function updateClock() {
  let h = new Date().getHours();
  let m = new Date().getMinutes();
  let s = new Date().getSeconds();
  let ampm = "AM";

  if (h > 12) {
    h = h - 12;
    ampm = "PM";
  }

  h = h < 10 ? "0" + h : h;
  m = m < 10 ? "0" + m : m;
  s = s < 10 ? "0" + s : s;

  hour.innerText = h;
  minute.innerText = m;
  second.innerText = s;
  ampm.innerText = ampm;
  setTimeout(() => {
    updateClock();
  }, 1000);
}

updateClock();
```
