<template>
  <div class="parallax-container">
    <div class="parallax-layer layer1" data-speed="0.3"></div>
    <div class="parallax-layer layer5" data-speed="-2"></div>
    <div class="parallax-layer layer2" data-speed="0.15"></div>
    <div class="parallax-layer layer3" data-speed="0"></div>
    <div class="parallax-layer layer4" data-speed="0"></div>
  </div>
</template>

<script>
/* eslint-disable space-before-function-paren, semi */
export default {
  name: 'ParallaxEffect',
  data() {
    return {
      scrollY: 0
    };
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      this.scrollY = window.scrollY;
      const layers = this.$el.querySelectorAll('.parallax-layer');
      layers.forEach(layer => {
        const speed = parseFloat(layer.dataset.speed);
        const yPos = -(this.scrollY * speed);
        layer.style.transform = `translateY(${yPos}px)`;
      });
    }
  }
};
</script>

<style scoped lang="scss">
.parallax-container {
  position: relative;
  height: 900px;
  overflow: hidden;
}

.parallax-layer {
  position: absolute;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
}

.layer1 {
  background-image: url('../assets/zelda-cloud-filled-layer.png');
}

.layer2 {
  background-image: url('../assets/zelda-landscape-layer.png');
  height: 110%;
  top: 0;
}

.layer3 {
  background-image: url('../assets/zelda-grass-layer.png');
}

.layer5 {
  background-image: url('../assets/zelda-title-layer.png');
  height: 70%;
}

.layer4 {
  background: linear-gradient(transparent, #3a4c34);
  height: 200px;
  bottom: 0;
}
</style>
