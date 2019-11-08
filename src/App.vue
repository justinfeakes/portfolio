<template>
  <div id="app">
  <!-- <div class="app-overlay"></div> -->
    
    <Card v-if="showCard" />

    <div class="background-top"></div>
    <div class="background-bottom"></div>

    <!-- <div class="grid">
      <div class="grid-row">
        <div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div>
      </div>
 <div class="grid-row">
       <div></div><div></div><div></div> <div></div><div></div><div></div><div></div><div></div><div></div>
      </div>
       <div class="grid-row">
        <div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div>
      </div>
       <div class="grid-row">
        <div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div>
      </div>
    </div> -->

    <div class="heading-text">
    <h1 class="header">
      Hey I'm Justin. I'm a developer / designer.
    <!-- <span>Hey </span><span>I'm </span> <span>Justin.</span> <span>I'm </span> <span>a </span> <span class="lighter">developer</span><span>/</span><span class="lighter">guitarist.</span> -->
    </h1>

    <!-- <p>hi</p> -->

    <button>Contact me</button>
    </div>
   <!-- <Guitar />-->
   <!-- <div class="intro">
     developer<br />guitarist
    </div> -->
  </div>
</template>

<script>
import Card from './components/Card.vue'
import Guitar from './components/guitar.vue'

export default {
  name: 'app',
  components: {
    Card, Guitar
  },
  data: function() {
    return {
      showCard: true
    }
  },
  mounted: function() {
    // setTimeout(() => {
    //   this.showCard = false;
    // }, 4400)
    //AIzaSyBLg__PVueiRZj7SUCw61Cvn6dgNp51RmE
  }
}
</script>

<style>
.grid {
 width: 300px;
 height: 200px;
 position: absolute;
 top: 200px;
 left: 200px;
 display: flex;
 flex-direction: column;
 justify-content: space-between;
}
.grid-row {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 100%;
  /* position: absolute; */
}

.grid-row div {
  height: 5px;
  width: 5px;
  background: grey;
  opaciTY: 0.4;
}
@keyframes enter-heading {
  0% { transform: translateY(20px); opacity: 0; }
  100% { transform: translateY(0); opacity: 1; }
}

@keyframes fade-in {
  0% { opacity: 0; }
  100% { opacity: 1; }
}

.heading-text {
  color: #333;
  position: absolute;
  font-weight: 900;
  top: 35vh;
  width: 70%;
  left: 0;
  right: 0;
  margin: 0 auto;
  text-align: center;
}

.heading-text h1 {
  animation: enter-heading 1s 3.3s forwards;
  opacity: 0;
  /* font-size: 40px; */
  margin-bottom:0;
}

.heading-text button {
  background: #0097A7;
  margin-top: 30px;
  padding-top: 10px;
  padding-bottom: 10px;
  padding-left: 40px;
  padding-right: 40px;
  border-radius: 100px;
  color: white;
  outline: none;
  animation: enter-heading 1s 3.4s forwards;
  font-size: 15px;
  font-weight: 700;
  border: none;
  opacity: 0;
  /* box-shadow: 0px 2px 4px rgb(185, 185, 185); */
}

.heading-text p {
  font-weight: 100;
  opacity: 0.7;
  animation: enter-heading 1s 3.3s forwards;
  opacity: 0;
}

/* h1 span {
  animation: enter-heading 1s forwards;
  margin-right: 7px;
  display:inline-block;
  opacity: 0;
} */

/* h1 span:nth-of-type(1) {
  animation-delay: 3.2s;
}

h1 span:nth-of-type(2) {
  animation-delay: 3.3s;
}

h1 span:nth-of-type(3) {
  animation-delay: 3.4s;
}

h1 span:nth-of-type(4) {
  animation-delay: 3.5s;
} */

/* h1 span:nth-of-type(5) {
  animation-delay: 3.6s;
}

h1 span:nth-of-type(6) {
  animation-delay: 3.7s;
}

h1 span:nth-of-type(7) {
  animation-delay: 3.8s;
} */

/* h1 span:nth-of-type(8) {
  animation-delay: 3.9s;
} */

@import url('https://fonts.googleapis.com/css?family=Roboto&display=swap');
@keyframes enter-top {
  0% { transform: translateY(100vh) }
  100% { transform: translateY(0) }
}

@keyframes enter-bottom {
  0% { transform: translateY(100vh) }
  100% { transform: translateX(0) }
}
.background-top {
  position: absolute;
  background: rgb(184, 184, 184);
  top: 0;
  left:0%;
  height: 100%;
  width: 100%;
  transform: translateX(-100vw);
  animation: .5s 3s enter-top forwards;
}

.background-bottom {
  position: absolute;
  background: white;
  /* background: rgb(243, 243, 243); */
  top: 0;
  left:0%;
  height: 100%;
  transform: translateX(100vw);
  width: 100%;
  animation: .6s 3.2s enter-bottom forwards;
}





.app-overlay {
  position: absolute;
  top: 50%;
  left: 0;
  width: 100%;
  height: 50%;
  background: white;
  opacity: 0.03;
}
.intro {
  position: absolute;
  top: 10%;
  left: 0;
  font-size: 70px;
  text-align: center;
  width: 100%;
  height: auto;
  color: white;
  font-weight: 700;
  line-height: 1;
  display: none;

}

.white-overlay {
  position: absolute;
  height: 100%;
  width: 40%;
  margin: 0 auto;
  left: 0;
  right: 0;
  background: white;
  top: 0;
}
.background-circles {
  width: 100vw;
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  flex-wrap: wrap;
  position: absolute;
  z-index: -1;
}

.circle {
  height: 10px;
  width: 10px;
  background: grey;
  border-radius: 100%;
  opacity: 0.1;
  margin: 10px;
}

* {
  box-sizing: border-box;
}

html, body {
    margin: 0;
    height: 100vh;
    width: 100vw;
  background: black;
    overflow: hidden;
}

#app {
font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  margin: 0;
  padding: 0;
  /* background: rgb(61, 61, 61); */
  height: 100vh;
  overflow: hidden;
  width: 100vw;
}

.animation-container {
  display: none;
  height: 60vh;
  width: 80%;
  margin: 0 auto;
  background: white;
  max-width: 600px;
  opacity: 0.3;
  margin-top: 20px;
}

@keyframes grow-vertical {
  0% { transform: scaleY(0); opacity: 0; }
  100% { transform: scaleY(1); opacity: 1; }
}

@keyframes grow-horizontal {
  0% {transform: scaleX(0); opacity: 0; }
  100% {transform: scaleX(1); opacity: 1; }
}

.developer {
  height: 100%;
  width: 100%;
  border: 1px solid rgb(151, 151, 151);
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  padding: 20px;
  box-sizing: border-box;
  justify-content: space-between;
  border-radius: 6px;
  animation: 1s grow-vertical forwards;
  transform-origin: top;
}

.box {
  background: #dcdcdc;
  opacity: 0;
  animation: 1s grow-horizontal forwards;
  transform-origin: left;
}

.box:nth-of-type(1) {
  width: 100%;
  height: 15%;
  animation-delay: 1s;
}

.box:nth-of-type(2) {
  width: 65%;
  height: 50%;
  animation-delay: 1.2s;
}

.box:nth-of-type(3) {
  width: 30%;
  height: 50%;
  animation-delay: 1.4s;
}

.box:nth-of-type(4) {
  width: 100%;
  height: 25%;
  animation-delay: 1.6s;
}


.description-container {
  display: block;
  width: 90vw;
  /* max-width: 300px; */
  margin: 0 auto;
  position: relative;
}

.description-box {
  display: inline-block;
  margin: 20px;

}

.description-box:nth-of-type(2) {
  opacity: 0.3;
}

html, body {
  margin: 0;
}

.row {
  width: 100vw;
  display: flex;
  height: 1vh;
}

.column {
  height: 100%;
  width: 1%;
  animation: 1s addColor forwards;
}

.active {
  background: white;
}

@keyframes addColor {
  0% { background: white; }
  100% { background: lightskyblue; }
}

@keyframes enter-note {
  0% { transform: scale(0) rotate(-90deg); }
  100% { transform: scale(1) rotate(0deg); }
}

.music-note {
  position: absolute;
  left: 0; right: 0;
  margin: 0 auto;
  top: 50vh;
  opacity: 0.6;
  animation: .5s enter-note forwards;
}
</style>
