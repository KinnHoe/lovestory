# lovestory
七夕
<!DOCTYPE html>
<!--
To change this license header, choose License Headers in Project Properties.
To change this template file, choose Tools | Templates
and open the template in the editor.
-->
<style>
    * {box-sizing: border-box;}
body {font-family: Verdana, sans-serif;}
.mySlides {display: none;}
img {vertical-align: middle;}

/* Slideshow container */
.slideshow-container {
  max-width: 1000px;
  position: relative;
  margin: auto;
}

/* Caption text */
.text {
  color: #f2f2f2;
  font-size: 15px;
  padding: 8px 12px;
  position: absolute;
  bottom: 8px;
  width: 100%;
  text-align: center;
}

/* Number text (1/3 etc) */
.numbertext {
  color: #f2f2f2;
  font-size: 12px;
  padding: 8px 12px;
  position: absolute;
  top: 0;
}

/* The dots/bullets/indicators */
.dot {
  height: 15px;
  width: 15px;
  margin: 0 2px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}

.active {
  background-color: #717171;
}

/* Fading animation */
.fade {
  -webkit-animation-name: fade;
  -webkit-animation-duration: 1.5s;
  animation-name: fade;
  animation-duration: 1.5s;
}

@-webkit-keyframes fade {
  from {opacity: .4} 
  to {opacity: 1}
}

@keyframes fade {
  from {opacity: .4} 
  to {opacity: 1}
}

/* On smaller screens, decrease text size */
@media only screen and (max-width: 300px) {
  .text {font-size: 11px}
}

.sticky {
  position: fixed;
  top: 0;
  width: 100%;
}



</style>

<?php
include "./includes/header.php";
?>

      <section class="container">
        <div class="content">
            <h1>Intro</h1>
            <p>Start it like this..</p>
        </div>
    </section>

    <section class="container">
        <div class="content">
            <h1>content 1</h1>
            <p>Start it like this..</p>
        </div>
    </section>

    <section class="container">
        <div class="content">
            <h1>content 2</h1>
            <p>Start it like this..</p>
        </div>
    </section>

    <section class="container">
        <div class="content">
            <h1>content 3</h1>
            <p>Start it like this..</p>
        </div>
    </section>

    <section class="container">
        <div class="content">
            <h1>content 4</h1>
            <p>Start it like this..</p>
        </div>
    </section>


    
<div style="width:550px; height: 300px; margin-left: 23%; -ms-transform: translateY(-25%); transform: translateY(-25%);"  id="block1">
<div class="mySlides fade">
  <img src="images/admin1.jfif" style="width:550px; height: 300px; border-radius: 15px;">
  <div class="text">Top 5 event in badminton club</div>
</div>

<div class="mySlides fade">
  <img src="images/palms_night_clouds_119839_3840x2160.jpg" style="width:550px; height: 300px; border-radius: 15px;">
  <div class="text">Top 5 event in badminton club</div>
</div>

<div class="mySlides fade" >
  <img src="images/test.png" style="width:550px; height: 300px; border-radius: 15px;">
  <div class="text">Top 5 event in badminton club</div>
</div>


<br>

<div style="text-align:center; display: none;">
  <span class="dot"></span> 
  <span class="dot"></span> 
  <span class="dot"></span> 
</div>

</div>
  

    <div id="set-height"></div>

    <video id="v0" tabindex="0", autobuffer preload style="border-radius: 15px;">
        <source type='video/mp4;codecs="avc1.42E01E, mp4a.40.2"' src="badminton.mp4"></source>
    </video>

    <script>

        enterView({
            selector: 'section',
            enter: function(el) {
                el.classList.add('entered');
            }
        })
    
        var frameNumber = 0, // start video at frame 0
        // lower numbers = faster playback
        playbackConst = 1000, 
        // get page height from video duration
        setHeight = document.getElementById("set-height"), 
        // select video element         
        vid = document.getElementById('v0'); 
        // var vid = $('#v0')[0]; // jquery option

    // dynamically set the page height according to video length
    vid.addEventListener('loadedmetadata', function() {
    setHeight.style.height = Math.floor(vid.duration) * playbackConst - 17500 + "px";
    });
    videolenght =  document.getElementById("set-height");


    // Use requestAnimationFrame for smooth playback
    function scrollPlay(){  
    var frameNumber  = window.pageYOffset/playbackConst;
    vid.currentTime  = frameNumber;
    window.requestAnimationFrame(scrollPlay);
    }

    window.requestAnimationFrame(scrollPlay);
    
    </script>

<script>
  video = document.getElementById("v0");
  slides = document.getElementsByClassName("mySlides");
  dots = document.getElementsByClassName("dot");

  
  
  var myScrollFunc = function() {
    var y = window.scrollY;
    if (y >= 6500) {
      video.className = "hide";
    } else {
      video.className = "show";
    }
    if (y >= 6500) {
      block1.className = "show1";
    } else {
      block1.className = "hide1";
    }
    
  };
  
  window.addEventListener("scroll", myScrollFunc);
  
  </script>


    <script>
window.onscroll = function() {myFunction()};

var header = document.getElementById("myHeader");
var block = document.getElementById("block");
var sticky = header.offsetTop;

function myFunction() {
  if (window.pageYOffset > sticky) {
    header.classList.add("sticky");
  } else {
    header.classList.remove("sticky");
  }

  if (window.pageYOffset > sticky) {
    block1.classList.add("sticky1");
  } else {
    block1.classList.remove("sticky1");
  }
 
}
</script>

<script>
var slideIndex = 0;
showSlides();

function showSlides() {
  var i;
  var slides = document.getElementsByClassName("mySlides");
  var dots = document.getElementsByClassName("dot");
  for (i = 0; i < slides.length; i++) {
    slides[i].style.display = "none";  
  }
  slideIndex++;
  if (slideIndex > slides.length) {slideIndex = 1}    
  for (i = 0; i < dots.length; i++) {
    dots[i].className = dots[i].className.replace(" active", "");
  }
  slides[slideIndex-1].style.display = "block";  
  dots[slideIndex-1].className += " active";
  setTimeout(showSlides, 2000); // Change image every 2 seconds
}
</script>

    

 
<!--Footer-->
<?php
include "./includes/footer.php";
?>





