# Sanjay1
##Stop watch

@font-face{
    font-family: digital-7;
    src: url(fonts/digital-7.ttf);
}

body {
    color: #FFFFFF;
    font-family: digital-7;
    text-align: center;  
    background-color: #000000;
    background-image: url(../images/clock.svg);
    background-repeat: no-repeat;
    background-position: center;
}
div{
    min-width: 20%;
    max-width: 100%;
    margin: 100px auto;
}

#heading{
    margin-top: 125px;
    text-decoration: underline;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif
}

#timer{
    font-size: 2.5em;
}

#start {
  margin: 20px auto;
  text-align: center;
  color: #DAD6D6;
  background: #48633B;
  border:solid 2px #35492C;
  border-radius:5px;
  padding:16px 40px 16px;
  letter-spacing: 2px;
  cursor:pointer;
}

#stop {
  margin: 20px 5px auto;
  text-align: center;
  color: #DAD6D6;
  background: #721329;
  border:solid 2px #590F20;
  border-radius:5px;
  padding:16px 40px 16px;
  letter-spacing: 2px;
  cursor:pointer;
}

#reset {
  margin: 20px auto;
  text-align: center;
  color: #DAD6D6;
  background: #564E58;
  border:solid 2px #3E383F;
  border-radius:5px;
  padding:16px 40px 16px;
  letter-spacing: 2px;
  cursor:pointer;
}

h2
{
  font-size: 46px;
  letter-spacing: 2px;
  margin: 200px 0 0 ;
}





<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="css/style.css">
    <title>Stop Watch</title>
</head>

<body>
    <center>
        <div>
            <h4 id="heading">DIGITAL STOPWATCH</h4>
            <h1 id="timer">0:0:0</h1>
            <button id="start" onclick="start();">Start</button>
            <button id="stop" onclick="stop();">Stop</button>
            <button id="reset" onclick="reset();">Reset</button>
        </div>
    </center>
</body>
<script src="js/app.js"></script>

</html>



var min = 0;
var sec = 0;
var miliSec = 0;
var timer;

function callTimer() {
    miliSec++;
    if (miliSec < 1000) {
        if (miliSec === 999) {
            miliSec = 0;
            sec++;
            if (sec === 60)  {
                sec = 0;
                min++;
            }
        }
    }
    else{
        miliSec = 0;
    }
    document.getElementById("timer").innerHTML = min + ":" + sec + ":" + miliSec;
}


function start() {
    document.getElementById("start").disabled = true;
    timer = setInterval(callTimer, 10);
}

function stop() {
    document.getElementById("start").disabled = false;
    clearInterval(timer);
}

function reset() {
    stop();
    min = 0;
    sec = 0;
    miliSec = 0;
    document.getElementById("timer").innerHTML = min + ":" + sec + ":" + miliSec;
}
