# clock
자바스크립트를 이용한 움직이는 시계만들기
![Animation](https://github.com/jung-chaewon/clock/assets/131144717/c2f8c21f-e660-473d-8017-f010cc4d751d)

## script
```javascript
  <script type="text/javascript">
    const deg = 6;
    // getting all hands of clock from html through id
    const hr = document.querySelector('#hr')
    const mn = document.querySelector('#mn');
    const sc = document.querySelector('#sc');

    setInterval(() => {
      let day = new Date();

      //setting the actual seconds minutes and hour in clock

      let ms = day.getMilliseconds() * deg;
      let hh = day.getHours() * 30;
      let mm = day.getMinutes() * deg;
      let ss = day.getSeconds() * deg + ms / 1000;

      //changing the degrees in the style as per the time

      hr.style.transform = `rotateZ(${(hh) + (mm / 12)}deg)`;
      mn.style.transform = `rotateZ(${mm}deg)`;
      sc.style.transform = `rotateZ(${ss}deg)`;

    }, 1);
  </script>
```


## css
``` css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  
  body {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background: #19172e;
    font-family: "sans";
  
  }
  
  @font-face {
    src: url("../font/sans.ttf");
    font-family: "sans";
  }
  
  .heading {
    color: white;
    text-align: center;
    position: absolute;
    left: 0;
    right: 0;
    top: 0;
    padding: 100px;
    line-height: 3vh;
  }
  
  .clock {
    width: 350px;
    height: 350px;
    display: flex;
    justify-content: center;
    align-items: center;
    background: url(../assets/clock.png);
    background-size: cover;
  }
  
  .clock:before {
    content: "";
    position: absolute;
    width: 15px;
    height: 15px;
    background: #fff;
    border-radius: 50%;
    z-index: 10000;
  }
  
  .clock .hour,
  .clock .min,
  .clock .sec {
    position: absolute;
  }
  
  .clock .hour,
  .hr {
    width: 160px;
    height: 160px;
  }
  
  .clock .min,
  .mn {
    width: 190px;
    height: 190px;
  }
  
  .clock .sec,
  .sc {
    width: 230px;
    height: 230px;
  }
  
  .hr,
  .mn,
  .sc {
    display: flex;
    justify-content: center;
    /* align-items: center; */
    position: absolute;
    border-radius: 50%;
  }
  
  .hr:before {
    content: "";
    position: absolute;
    width: 6px;
    height: 80px;
    background: #bb86fc;
    z-index: 10;
    border-radius: 6px 6px 0 0;
  }
  
  .mn:before {
    content: "";
    position: absolute;
    width: 4px;
    height: 90px;
    background: #fff;
    z-index: 11;
    border-radius: 6px 6px 0 0;
  }
  
  .sc:before {
    content: "";
    position: absolute;
    width: 2px;
    height: 150px;
    background: #70efde;
    z-index: 12;
    border-radius: 6px 6px 0 0;
  }
  
  footer {
    text-align: center;
    color: white;
    font-size: 1rem;
    position: absolute;
    bottom: 0;
    margin-bottom: 0;
    padding: 5px;
    line-height: 3vh;
  }
  
  footer a:visited {
    color: inherit;
  }
```
## index
``` html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Clock</title>
  <link rel="stylesheet" href="css/style.css">
  <link rel="icon" href="assets/favicon.png">

</head>

<body>
  <h2 class="heading">
    Clock
  </h2>
  <div class="clock">
    <div class="hour">
      <div class="hr" id="hr"></div>
    </div>
    <div class="min">
      <div class="mn" id="mn"></div>
    </div>
    <div class="sec">
      <div class="sc" id="sc"></div>
    </div>
  </div>

</body>
```
