<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <audio src="./assets/liudehua.mp3"></audio>
    <div class="bd">
      <div class="left"></div>
      <div class="right"></div>
    </div>
    <div class="boxRot">
      <ul>
        <li><img src="./assets/1.jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/2.jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/5.jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/4.jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/3.jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/6.jpg" height="100%" width="100%" /></li>
      </ul>
      <ul>
        <li><img src="./assets/caishen6.jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/caishen5.jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/caishen4.jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/caishen3.jpeg" height="100%" width="100%" /></li>
        <li><img src="./assets/caishen2.jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/caishen1.jpeg" height="100%" width="100%" /></li>
      </ul>
      <ul>
        <li><img src="./assets/11 (1).jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/11 (2).jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/11 (3).jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/11 (4).jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/11 (5).jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/11 (6).jpg" height="100%" width="100%" /></li>
      </ul>
      <ul>
        <li><img src="./assets/gong6.jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/gong5.jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/gong4.jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/gong3.jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/gong2.jpg" height="100%" width="100%" /></li>
        <li><img src="./assets/gong1.jpg" height="100%" width="100%" /></li>
      </ul>
    </div>
    <div class="boxTex">
      <span>恭</span><span>喜</span><span>发</span><span>财</span><span>中</span><span>大</span><span>奖</span
      ><span>哈</span>
    </div>
    <div class="box">
      <ul>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
      </ul>
      <span></span>
      <button>开始</button><button>停止</button>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  components: {
    // HelloWorld,
  },
  mounted() {
    this.start();
  },
  methods: {
    start() {
      var btnArr = document.getElementsByTagName('button');
      var _box = document.querySelector('.box');
      var liArr = _box.querySelectorAll('li');
      var span = _box.querySelector('span');
      var _boxRot = document.querySelector('.boxRot');
      var _ulRot = _boxRot.querySelectorAll('ul');
      var _audio = document.querySelector('audio');
      var _left = document.querySelector('.left');
      var _right = document.querySelector('.right');
      var timer = null;
      // var timer1 = null;
      // var num = [],
      //   n;
      // var sum = 0;
      btnArr[0].onclick = function () {
        clearInterval(timer);
        _left.style.transform = 'translateY(563px)';
        _left.style.animation = 'xia 15s linear infinite alternate 2s';
        _right.style.transform = 'translateY(563px)';
        _right.style.animation = 'xia 15s linear infinite alternate 2s';
        _audio.play();
        for (var i = 0; i < _ulRot.length; i++) {
          _ulRot[i].style.animation = 'zhuan 5s linear infinite';
        }
        timer = setInterval(function () {
          span.innerHTML = parseInt(Math.random() * 16 + 1);
          var num = [];
          for (var i = 0; ; i++) {
            var bool = true;
            var n = parseInt(Math.random() * 33 + 1);
            for (var j = 0; j < num.length; j++) {
              if (n == num[j]) {
                bool = false;
              }
            }
            if (bool) {
              num.push(n);
            }
            if (num.length == 6) {
              break;
            }
          }
          for (var s = 0; s < liArr.length; s++) {
            liArr[s].innerHTML = num[s];
          }
        }, 100);
      };
      btnArr[1].onclick = function () {
        clearInterval(timer);
      };
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
* {
  padding: 0;
  margin: 0;
  list-style: none;
}
html,
body {
  height: 5000px;
  width: 1240px;
  margin: 0 auto;
}
body {
  background: url('./assets/b2_bg.jpg') repeat;
  background-position: center top;
  position: relative;
}
.boxRot {
  height: 350px;
  width: 900px;
  border: 1px solid #000;
  background: url('./assets/b1_bg.jpg') no-repeat;
  margin: 0 auto;
  cursor: pointer;
  position: relative;
  top: 10px;
  box-shadow: 0 0 10px 2px;
}
.boxRot ul {
  height: 200px;
  width: 200px;
  position: absolute;
  top: 50%;
  margin-left: 10px;
  transform: translateY(-50%);
  transform-style: preserve-3d;
  transform-origin: 50% 50%;
}
@keyframes zhuan {
  0% {
    transform: translateY(-50%) rotateX(0deg) rotateY(0deg);
  }
  100% {
    transform: translateY(-50%) rotateX(360deg) rotateY(360deg);
  }
}
.boxRot ul:nth-child(2) {
  left: 225px;
}
.boxRot ul:nth-child(3) {
  left: 450px;
}
.boxRot ul:nth-child(4) {
  left: 675px;
}
.boxRot li {
  height: 100%;
  width: 100%;
  position: absolute;
  top: 0;
  left: 0;
  color: #fff;
}
.boxRot li:nth-child(1) {
  transform: rotateX(90deg) translateZ(100px);
}
.boxRot li:nth-child(2) {
  transform: rotateX(-90deg) translateZ(100px);
}
.boxRot li:nth-child(3) {
  transform: rotateY(-90deg) translateZ(100px);
}
.boxRot li:nth-child(4) {
  transform: rotateY(90deg) translateZ(100px);
}
.boxRot li:nth-child(5) {
  transform: translateZ(100px);
}
.boxRot li:nth-child(6) {
  transform: rotateY(180deg) translateZ(100px);
}
.box {
  height: 100px;
  width: 900px;
  position: relative;
  left: 50%;
  top: 100px;
  transform: translate(-50%);
}
.box button {
  float: left;
  margin-top: 30px;
  width: 80px;
  height: 30px;
  cursor: pointer;
}
.box li {
  height: 80px;
  line-height: 80px;
  text-align: center;
  width: 80px;
  background-color: #ccc;
  color: red;
  float: left;
  margin: 10px;
  font-size: 30px;
  font-weight: 700;
  border-radius: 10px;
  box-shadow: 0 0 10px 2px #000;
}
.box span {
  display: block;
  color: blue;
  height: 80px;
  text-align: center;
  line-height: 80px;
  width: 80px;
  background-color: #ccc;
  float: left;
  margin: 10px;
  font-size: 30px;
  font-weight: 700;
  border-radius: 10px;
  box-shadow: 0 0 10px 2px #000;
}
.boxTex {
  width: 900px;
  height: 70px;
  position: relative;
  left: 60%;
  top: 40px;
  transform: translate(-50%);
}
.boxTex span {
  font-size: 60px;
  font-weight: 700;
  position: relative;
  color: red;
  animation: bianshuai 1.6s linear infinite alternate;
}
@keyframes bianshuai {
  0% {
    top: 0;
    color: red;
    text-shadow: 1px 1px 2px yellowgreen;
  }
  100% {
    top: 30px;
    color: cyan;
    text-shadow: 1px 1px 2px pink;
  }
}
.boxTex span:nth-child(2) {
  animation-delay: 0.2s;
}
.boxTex span:nth-child(3) {
  animation-delay: 0.4s;
}
.boxTex span:nth-child(4) {
  animation-delay: 0.6s;
}
.boxTex span:nth-child(5) {
  animation-delay: 0.8s;
}
.boxTex span:nth-child(6) {
  animation-delay: 1s;
}
.boxTex span:nth-child(7) {
  animation-delay: 1.2s;
}
.boxTex span:nth-child(8) {
  animation-delay: 1.4s;
}
.bd {
  width: 1210px;
  height: 600px;
  position: absolute;
  left: 50%;
  transform: translate(-50%);
}
.left {
  width: 104px;
  height: 520px;
  background: url(./assets/80g58PICckm_1024.jpg) -84px -101px no-repeat;
  position: absolute;
  top: -520px;
  left: 0px;
  transition: all 1s linear;
  transform-origin: 50% 50%;
}
.right {
  width: 104px;
  height: 520px;
  background: url(./assets/80g58PICckm_1024.jpg) -478px -101px no-repeat;
  position: absolute;
  top: -520px;
  right: 0px;
  transition: all 1s linear;
  transform-origin: 50% 50%;
}
@keyframes xia {
  0% {
    width: 104px;
    height: 520px;
  }
  100% {
    width: 0px;
    height: 0px;
  }
}
</style>
