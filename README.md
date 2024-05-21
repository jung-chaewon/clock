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

