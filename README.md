# digital-clock
![Animation](https://github.com/jung-chaewon/digital-clock/assets/131144717/d598d172-053c-493c-a7f2-a7e505013fd7)

자바스크립트를 이용한 디지털 시계 만들기
### 자바스크립트
```javascript
  const hour = document.getElementById("hour");
const minute = document.getElementById("minute");
const seconds = document.getElementById("seconds");
const ampm = document.getElementById("ampm");
// 10보다 작은 숫자 앞에 0을 추가하는 함수
function formatTime(time) {
  return time.toString().padStart(2, "0");
}

// 시간이 12시 이상인지 여부를 판별하여 오전(AM) 또는 오후(PM) 반환
function isAmPm(hours) {
  return hours >= 12 ? "오후" : "오전";
}

function clock() {
  const date = new Date();

  let h = date.getHours();  // 현재 시 (24시간제)
  let m = date.getMinutes();  // 현재 분
  let s = date.getSeconds();  // 현재 초

  hour.textContent = formatTime(h);
  minute.textContent = formatTime(m);
  seconds.textContent = formatTime(s);
  ampm.textContent = isAmPm(h);
}
setInterval(clock, 1000);

```
### css
```css
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "sans";
  }
  
  @font-face {
    src: url("font/sans.ttf");
    font-family: "sans";
  }
  
  .heading {
    color: white;
    font-size: 2rem;
    text-align: center;
    position: absolute;
    top: 0;
    padding: 100px;
  }
  
  section {
    position: absolute;
    width: 100%;
    height: 100vh;
    background: #19172e;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .clock {
    position: relative;
    width: 450px;
    height: 150px;
    background: rgba(255, 255, 255, 0.05);
    box-shadow: 0 15px 25px rgba(0, 0, 0, 0.1);
    z-index: 1000;
    border-radius: 20px;
    backdrop-filter: blur(20px);
  }
  
  .clock .container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
  }
  
  .clock .container h2 {
    font-size: 3.5rem;
    color: #fff;
  }
  
  .clock .container h2:nth-child(odd) {
    padding: 5px 10px;
    border-radius: 10px;
    background: rgba(255, 255, 255, 0.05);
    box-shadow: 0 15px 25px rgba(0, 0, 0, 0.2);
  }
  
  #ampm {
    position: relative;
    top: 30px;
    font-size: 1rem;
    color: #fff;
    font-weight: 700;
  }
  
```
### index
```html
  <!DOCTYPE html>
<html lang="en">
  <head>
	<meta charset="UTF-8" />
	<meta http-equiv="X-UA-Compatible" content="IE=edge" />
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
	<title>Digital Clock</title>
	<link rel="stylesheet" href="css/style.css" />
	<link rel="shortcut icon" href="assets/favicon.png" type="image/x-icon" />
	<script src="scirpt/script.js" defer></script>
  </head>
  <body>
	<section>
  	<h3 class="heading">Digital Clock</h3>
  	<div class="clock">
    	<div class="container">
      	<h2 id="hour">00</h2>
      	<h2 class="dot">:</h2>
      	<h2 id="minute">00</h2>
      	<h2 class="dot">:</h2>
      	<h2 id="seconds">00</h2>
      	<span id="ampm">AM</span>
    	</div>
  	</div>
	</section>

  </body>
</html>

```
