<template>
<div class="home" id="start">
  <div class="home-parallax">
    <div class="home-parallax__layer lawyer-10" data-type="parallax" data-depth="0"></div>
    <header class="home-header" data-type="parallax" data-depth="-0.1">
      <h1 class="home-header__title">{{ msg }}</h1>
      <p class="home-header__subtitle">Front-End Developer</p>
    </header>
    <div class="home-parallax__layer lawyer-9" data-type="parallax" data-depth="0.1"></div>
    <div class="home-parallax__layer lawyer-8" data-type="parallax" data-depth="0.01"></div>
    <div class="home-parallax__layer lawyer-7" data-type="parallax" data-depth="0.05"></div>
    <div class="home-parallax__layer lawyer-6" data-type="parallax" data-depth="0.005"></div>
    <div class="home-parallax__layer lawyer-5" data-type="parallax" data-depth="1"></div>
    <div class="home-parallax__layer lawyer-4" data-type="parallax" data-depth="0.8"></div>
    <div class="home-parallax__layer lawyer-3" data-type="parallax" data-depth="-0.6"></div>
    <div class="home-parallax__layer lawyer-2" data-type="parallax" data-depth="-0.7"></div>
    <div class="home-parallax__layer lawyer-1" data-type="parallax" data-depth="-0.8"></div>
  </div>
</div>
</template>

<script>
export default {
  name: 'Home',
  props: {
    msg: String
  }
}

let lastScrollPosition = 0;
let ticking = false;

function parallaxEffect(scrollTopOffset) {
  let move;
  let depth;
  let translate3d;
  let layers = document.querySelectorAll("[data-type='parallax']");
  for (let layer of layers) {    // don't actually do this
    depth = layer.getAttribute('data-depth')
    move = (scrollTopOffset * depth)
    translate3d = 'translate3d(0, ' + move + 'px, 0)'
    layer.style['-webkit-transform'] = translate3d
    layer.style['-moz-transform'] = translate3d
    layer.style['-ms-transform'] = translate3d
    layer.style['-o-transform'] = translate3d
    layer.style.transform = translate3d
  }
}

window.addEventListener('scroll', function() {
  lastScrollPosition = window.scrollY;
  if (!ticking) {

    window.requestAnimationFrame(function() {
      parallaxEffect(lastScrollPosition);
      ticking = false;
    });

    ticking = true;

  }

});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.home {
  height: 650px;
  margin: 0 auto;
  overflow: hidden;
}
.home-header {
  text-align: center;
  position: fixed;
  left: 0;
  right: 0;
  top: 9rem;
    z-index: -1;
  &__title {
    font-size: 3rem;
    margin-bottom: 0;
    color: #2c3e50;
  }
  &__subtitle {
    font-size: 1.5rem;
    margin-top: 0;
    color: #34495e;
  }
}
.home-parallax {
  position: relative;
  z-index: -1;
  height: inherit;
  overflow: hidden;
  &__layer {
    z-index: -2;
    background-repeat: repeat-x;
    position: fixed;
    height: inherit;
    width: 100%;
    background-position: bottom center;
    background-size: contain;
    min-width: 700px;
  }
}
.lawyer-1 {
  background-image: url("../assets/parallax/layer-1.png");
}
.lawyer-2 {
  background-image: url("../assets/parallax/layer-2.png");
}
.lawyer-3 {
  background-image: url("../assets/parallax/layer-3.png");
}
.lawyer-4 {
  background-image: url("../assets/parallax/layer-4.png");
}
.lawyer-5 {
  background-image: url("../assets/parallax/layer-5.png");
}
.lawyer-6 {
  background-image: url("../assets/parallax/layer-6.png");
}
.lawyer-7 {
  background-image: url("../assets/parallax/layer-7.png");
}
.lawyer-8 {
  background-image: url("../assets/parallax/layer-8.png");
}
.lawyer-9 {
  background-image: url("../assets/parallax/layer-9.png");
}
.lawyer-10 {
  background-image: url("../assets/parallax/layer-10.png");
  background-repeat: repeat-x;
  background-position: top;
  background-size: cover;
}
@media all and (max-width:991px) {
  .home-parallax {
    // display: none;
  }
}
</style>
