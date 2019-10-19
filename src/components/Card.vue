<template>
  <div class="card">
    <div id="container" ref="cardContainer">
      <div id="inner" ref="cardInner">

      <div class="background-circles left">
      <div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div>
    </div>

    <div class="background-circles right">
      <div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div><div class="circle"></div>
    </div>
        <div class="overlay"></div>
        <p class="background-text top">
          DEVELOPER
        </p>

        <p class="background-text bottom">
          GUITARIST
        </p>
        <!--i'm a software developer and guitarist-->

        <div class="laptop">
          <div class="screen">
            <div class="text-bar"></div>
            <div class="text-bar"></div>
            <div class="text-bar"></div>
          </div>
          <div class="base"></div>
        </div>
        

        <div class="atom-container">
          <div class="atom first"></div>
          <div class="atom second"></div>
          <div class="atom third"></div>

          <div class="atom fourth"></div>
          <div class="atom fifth"></div>
          <div class="atom sixth"></div>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  mounted: function() {
    var container = document.getElementById("container"),
    inner = document.getElementById("inner");

  // Mouse
  var mouse = {
    _x: 0,
    _y: 0,
    x: 0,
    y: 0,
    updatePosition: function(event) {
      var e = event || window.event;
      this.x = e.clientX - this._x;
      this.y = (e.clientY - this._y) * -1;
    },
    setOrigin: function(e) {
      this._x = e.offsetLeft + Math.floor(e.offsetWidth / 2);
      this._y = e.offsetTop + Math.floor(e.offsetHeight / 2);
    },
    show: function() {
      return "(" + this.x + ", " + this.y + ")";
    }
  };

  // Track the mouse position relative to the center of the container.
  mouse.setOrigin(container);

  //-----------------------------------------

  var counter = 0;
  var updateRate = 10;
  var isTimeToUpdate = function() {
    return counter++ % updateRate === 0;
  };

  //-----------------------------------------

  var onMouseEnterHandler = function(event) {
    update(event);
  };

  var onMouseLeaveHandler = function() {
    inner.style = "";
  };

  var onMouseMoveHandler = function(event) {
    if (isTimeToUpdate()) {
      update(event);
    }
  };

  //-----------------------------------------

  var update = function(event) {
    mouse.updatePosition(event);
    updateTransformStyle(
      (mouse.y / inner.offsetHeight / 2).toFixed(2),
      (mouse.x / inner.offsetWidth / 2).toFixed(2)
    );
  };

  var updateTransformStyle = function(x, y) {
    var style = "rotateX(" + x + "deg) rotateY(" + y + "deg)";
    inner.style.transform = style;
    inner.style.webkitTransform = style;
    inner.style.mozTransform = style;
    inner.style.msTransform = style;
    inner.style.oTransform = style;
  };

  //-----------------------------------------

  container.onmouseenter = onMouseEnterHandler;
  container.onmouseleave = onMouseLeaveHandler;
  container.onmousemove = onMouseMoveHandler;
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

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
bottom: 0!important;
top: unset;
}

@keyframes atom-move {
  0%, 100% { transform: translateX(0) translateY(0); opacity: 0;}
  10% { opacity: 1; }
  30%{ transform: translateX(20px) translateY(-20px); opacity: initial;}
  70%{ transform: translateX(-10px) translateY(-10px)}
  80% { opacity: initial; }
}
@keyframes atom-move-alternate {
  0%, 100% { transform: translateX(0) translateY(0); opacity: 0;}
  10% { opacity: 1; }
  30%{ transform: translateX(-10px) translateY(20px); opacity: initial;}
  70%{ transform: translateX(30px) translateY(10px)}
  80% { opacity: initial; }
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
  box-shadow:0px 0px 20px red;
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
  height: 90%;
  width: 90%;
  margin-top: 5%;
  margin-left: 5%;
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
  top: 0; left: 0;
  width: 40%;
}

.background-circles.right {
  top: 0; right: 0;
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
