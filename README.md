<!DOCTYPE HTML>
<html>
<head>
<style>
p {
  text-align: center;
  font-size: 60px;
}

</style>
</head>
<body bgcolor="cyan">

  <center><h1> Echo and Liam Anniversary </h1>
  <!-- <h1 id="newYear"></h1> -->
  </center>

<p>The lovers have been togetherr for</p>
<p id="demo"></p>
<br>
<p> Here is the count down to a special day</p>
<p id="bday"></p>
<br>
  <h1><right>💕</right></h1>



<script>
// Set the date we're counting down to

var da = new Date();
var currentYear = da.getFullYear();
var nextYear = currentYear + 1;
var countDownDate = new Date("Aug 8, "+ nextYear +" 00:00:00").getTime();
var anniversaryDate = new Date("Feb 25, 2023 00:00:00").getTime();
  
// Update the count down every 1 second
var x = setInterval(function() {

    // Get todays date and time
    var now = new Date().getTime();
    
    // Find the distance between now an the count down date
    var Bdaydistance = countDownDate - now;
    var distance =   now - anniversaryDate;
    // console.log(distance)

    // Time calculations for days, hours, minutes and seconds
    var years = Math.floor(distance / (1000 * 60 * 60 * 24 * 365));
    var months = Math.floor((distance % (1000 * 60 * 60 * 24 * 365)) / (1000 * 60 * 60 * 24 * 30));
    var days = Math.floor((distance % (1000 * 60 * 60 * 24 * 30)) /(1000 * 60 * 60 * 24));
    var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
    var seconds = Math.floor((distance % (1000 * 60)) / 1000);
    
    // Output the result in an element with id="demo"
    document.getElementById("demo").innerHTML =years + "y " +months +"m " + days + "d " + hours + "h "
    + minutes + "m " + seconds + "s ";
  

    var Bdayyears = Math.floor(Bdaydistance / (1000 * 60 * 60 * 24 * 360));
    var bdaysmonths = Math.floor((Bdaydistance % (1000 * 60 * 60 * 24 * 365)) / (1000 * 60 * 60 * 24 * 30));
    var Bdaydays = Math.floor((Bdaydistance % (1000 * 60 * 60 * 24 * 30)) /(1000 * 60 * 60 * 24));
    var Bdayhours = Math.floor((Bdaydistance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    var Bdayminutes = Math.floor((Bdaydistance % (1000 * 60 * 60)) / (1000 * 60));
    var Bdayseconds = Math.floor((Bdaydistance % (1000 * 60)) / 1000);

    document.getElementById("bday").innerHTML = bdaysmonths +"m "+Bdaydays + "d " + Bdayhours + "h "
    + Bdayminutes + "m " + Bdayseconds + "s ";

    //document.getElementById("newYear").innerHTML = nextYear + "!";
    
    // If the count down is over, write some text 
    if (distance < 0) {
        clearInterval(x);
        document.getElementById("demo").innerHTML = "EXPIRED";
    }
}, 1000);
</script>

</body>
</html>
