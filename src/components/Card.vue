<template>
  <div class="letter">
    <div class="tall">
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
    </div>

    <div class="dot">
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
    </div>

    <div class="bottom">
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
      <div />
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  mounted: function() {
    // onmousemove = function(e){
    //   elements.forEach((element) => {
    //     let x = Math.floor((Math.random() * 10) + 1)
    //     let y = Math.floor((Math.random() * 10) + 1)
    //     element.style.transform = flag ? `translateX(${x}px) translateY(${y}px)` : `translateX(-${startX}px) translateY(-${startY}px)`;

    //   })
    //   // console.log("mouse location:", e.clientX, e.clientY)
    // }

    let elements = [
      ...document.querySelectorAll(".tall div"),
      ...document.querySelectorAll(".dot div"),
      ...document.querySelectorAll(".bottom div")
    ];
    let flag = true;

    elements.forEach(element => {
      console.log(element);
      let startX = Math.floor(Math.random() * 200 + 1);
      let startY = Math.floor(Math.random() * 200 + 1);

      
      let endX = Math.floor(Math.random() * 5 + 1);
      let endY = Math.floor(Math.random() * 5 + 1);
      
      element.style.transform = flag
        ? `translateX(${startX}px) translateY(${startY}px)`
        : `translateX(-${startX}px) translateY(-${startY}px)`;
      element.style.transitionDuration = Math.random() * 2.0 + 1 + "s";
      flag = !flag;
      setTimeout(() => {
        element.style.opacity = "1";
        element.style.transform = flag
        ? `translateX(${endX}px) translateY(0px)`
        : `translateX(-${endX}px) translateY(-0}px)`;
      }, 500);

      // setTimeout(() => {
      //   elements.forEach(element => { element.style.transition = "2s all linear" });
      //   setInterval(() => {
      //     elements.forEach(element => {
      //       let x = Math.floor(Math.random() * 10 + 1);
      //       let y = Math.floor(Math.random() * 10 + 1);
      //       element.style.transform = `translateX(${x}px) translateY(${y}px)`;
      //     });
      //   }, 2500);
      // }, 1000);
    });
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.letter {
  position: absolute;
  left: 0;
  right: 0;
  margin: 0 auto;
  /* border: 1px solid red; */
  height: 130px;
  width: 90px;
  top: calc(50% - 65px);
}
/* .letter * {
  background: rgb(209, 209, 209);
} */
.dot {
  position: absolute;
  top: 0;
  right: 0;
  width: 30px;
  display: flex;
  height: 30px;
  flex-direction: row;
  flex-wrap: wrap;
}
.tall {
  position: absolute;
  top: 40px;
  right: 0;
  width: 30px;
  height: 60px;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
.bottom {
  position: absolute;
  bottom: 0;
  width: 90px;
  height: 30px;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

.bottom div,
.tall div,
.dot div {
  width: 5px;
  height: 5px;
  background: rgb(209, 209, 209);
  transition: 1.5s all cubic-bezier(0.42, 0, 0, 1.38);
  /* display: inline-block; */
  opacity: 0;
}
.bottom div:hover,
.tall div:hover,
.dot div:hover {
  background: red;
}

.active {
  /* color: rgb(238, 238, 110)!important;
  opacity: 0.3!important;
  background: none; */
}

.background-text {
  position: absolute;
  font-size: 100px;
  width: 100%;
  text-align: center;
  top: -50px;
  left: 0;
  opacity: 0.02;
  line-height: 1;
  font-weight: 700;
}

.background-text.bottom {
  bottom: 0 !important;
  top: unset;
}

@keyframes atom-move {
  0%,
  100% {
    transform: translateX(0) translateY(0);
    opacity: 0;
  }
  10% {
    opacity: 1;
  }
  30% {
    transform: translateX(20px) translateY(-20px);
    opacity: initial;
  }
  70% {
    transform: translateX(-10px) translateY(-10px);
  }
  80% {
    opacity: initial;
  }
}
@keyframes atom-move-alternate {
  0%,
  100% {
    transform: translateX(0) translateY(0);
    opacity: 0;
  }
  10% {
    opacity: 1;
  }
  30% {
    transform: translateX(-10px) translateY(20px);
    opacity: initial;
  }
  70% {
    transform: translateX(30px) translateY(10px);
  }
  80% {
    opacity: initial;
  }
}
.atom-container {
  position: absolute;
  height: 400px;
  width: 500px;
  left: 0;
  right: 0;
  margin: auto;
  top: 30%;
}
.atom {
  height: 8px;
  width: 8px;
  border-radius: 100%;
  position: absolute;
  opacity: 0;
}

.atom.first {
  top: 30%;
  left: 10%;
  background: red;
  box-shadow: 0px 0px 20px red;
  animation-delay: 0.1;
  animation: 20s atom-move infinite;
}

.atom.second {
  top: 15%;
  right: 10%;
  background: yellow;
  box-shadow: 0px 0px 20px yellow;
  animation-delay: 1s;
  animation: 15s atom-move infinite;
}

.atom.third {
  top: 40%;
  right: 15%;
  background: orange;
  box-shadow: 0px 0px 20px orange;
  animation: 20s atom-move-alternate infinite;
  animation-delay: 0.5;
}

.atom.fourth {
  background: red;
  box-shadow: 0px 0px 20px red;
  top: 60%;
  height: 6px;
  width: 6px;
  right: 5%;
  animation-delay: 1s;
  animation: 20s atom-move-alternate infinite;
}

.atom.fifth {
  top: 45%;
  left: 5%;
  height: 6px;
  width: 6px;
  background: yellow;
  box-shadow: 0px 0px 20px yellow;
  animation-delay: 1.5s;
  animation: 13s atom-move infinite;
}

.reflect {
  transform: rotate(-180deg);
  opacity: 0.05;
}

.laptop {
  width: 250px;
  height: 150px;
  margin: 0 auto;
  margin-top: 50px;
  position: relative;
}
.laptop .screen {
  position: absolute;
  height: 90%;
  width: 90%;
  top: 0;
  left: 5%;
  background: white;
  border: 7px solid rgb(73, 73, 73);
  border-bottom: none;
  border-top-right-radius: 6px;
  border-top-left-radius: 6px;
}

.laptop .screen .text-bar {
  position: absolute;
  top: 10%;
  left: 0;
  width: 90%;
  background: rgb(175, 175, 175);
  opacity: 0.3;
  height: 20%;
  left: 5%;
}

.laptop .screen .text-bar:nth-of-type(2) {
  top: 40%;
  width: 60%;
}

.laptop .screen .text-bar:nth-of-type(3) {
  top: 70%;
  width: 75%;
}

.laptop .base {
  background: rgb(175, 175, 175);
  height: 10%;
  position: absolute;
  width: 100%;
  left: 0;
  bottom: 0;
  box-shadow: 0px -2px 4px dimgrey;
  border-bottom-left-radius: 50px;
  border-bottom-right-radius: 50px;
}

.card {
  width: 100vw;
  height: 100vh;
  margin: 0 auto;
  position: absolute;
  top: 0;
  left: 0;
}
#container {
  perspective: 35px;
  margin: 0 auto;
  height: 100%;
  width: 100%;
}

#inner {
  height: 100%;
  width: 100%;
  /* margin-top: 5%;
  margin-left: 5%; */
  background: radial-gradient(rgb(41, 41, 41), rgb(19, 19, 19));
  box-shadow: 2px 2px 50px rgba(0, 0, 0, 0.2);
  transition: transform 0.5s;
  -webkit-transition: transform 0.5s;
  -moz-transition: transform 0.5s;
  -o-transition: transform 0.5s;
  padding-top: 200px;
  font-size: 20px;
  overflow: visible;
  position: relative;
  color: white;
}

.overlay {
  position: absolute;
  height: 100%;
  width: 50%;
  background: white;
  left: 0;
  top: 0;
  opacity: 0.05;
}

.background-circles {
  display: flex;
  height: 100%;
  flex-direction: row;
  justify-content: space-evenly;
  flex-wrap: wrap;
  position: absolute;
  z-index: 999;
  display: none;
}
.background-circles.left {
  top: 0;
  left: 0;
  width: 40%;
}

.background-circles.right {
  top: 0;
  right: 0;
  width: 40%;
}

.circle {
  height: 10px;
  width: 10px;
  background: grey;
  //border-radius: 100%;
  opacity: 0.1;
  margin: 8%;
}
</style>
