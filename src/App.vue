<template>
  <div id="app">
  

    <Card />
   <!-- <Guitar />-->
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
  mounted: function() {
    //AIzaSyBLg__PVueiRZj7SUCw61Cvn6dgNp51RmE
  }
}
</script>

<style>

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

#app {
  font-family: 'Calibri', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
  padding: 0;
  padding-top: 15vh;
  background: rgb(19, 19, 19);
  height: 100vh;
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
