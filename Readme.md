<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ANALOG SAAT</title>
</head>

<body>
  <div class="clock">
    <div class="hour"></div>
    <div class="minute"></div>
    <div class="second"></div>
    <div class="cap"></div>
  </div>

  <style>
    body {
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: black;
    border: 5px black solid;
    margin-top: 50px;
    }

    .clock {
      background: url("indir.png") no-repeat;
      background-size: cover;
      width: 90vmin;
      height: 90vmin;
      position: relative;
      background-color: black;
      border-radius: 400px;
    }



    .hour,
    .minute,
    .second,
    .cap {
      transform-origin: center top;
      border-radius: 1vmin;
      position: absolute;
      top: 50%;
      left: 50%;
    }

    .hour {
      width: 2vmin;
      height: 24vmin;
      background-color: black;
      margin-left: -1vmin;
    }

    .minute {
      width: 1.2vmin;
      height: 38vmin;
      background-color: black;
      margin-left: -.6vmin;
    }

    .second {
      width: .6vmin;
      height: 40vmin;
      background-color: red;
      margin-left: -.3vmin;
    }

    .cap {
      width: 4vmin;
      height: 4vmin;
      background-color: red;
      margin-left: -2vmin;
      margin-top: -2vmin;
      border-radius: 50%;
    }

    
  </style>

  <script>
    const hour = document.querySelector(".hour");
    const minute = document.querySelector(".minute");
    const second = document.querySelector(".second");
    const f = x => x.toString().length == 1 ? "0" + x : x;


    function showTime() {
      let time = new Date();
      let h = time.getHours();
      let m = time.getMinutes();
      let s = time.getSeconds();
      let ao = 180; // angle offset
      let secondAngle = (s / 60) * 360;
      let minuteAngle = (m / 60) * 360 + secondAngle / 60;
      let hourAngle = (h % 12 / 12) * 360 + minuteAngle / 12;
      hour.style.transform = `rotate(${hourAngle + ao}deg)`;
      minute.style.transform = `rotate(${minuteAngle + ao}deg)`;
      second.style.transform = `rotate(${secondAngle + ao}deg)`;
      }

    setInterval(showTime, 1000);
  </script>


  <!--
          You can change time for testing:     
          time.setHours(time.getHours() + 2);
          time.setMinutes(time.getMinutes() + 33); 
        -->

</body>

</html>
