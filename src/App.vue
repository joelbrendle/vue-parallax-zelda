<template>
  <div>
    <ParallaxEffect />
    <div class="filler-box">
    </div>
    <p>Joel is cool</p>
</div>
</template>

<script>
import ParallaxEffect from './components/ParallaxEffect'

export default {
  name: 'App',
  components: {
    ParallaxEffect
  }
}
</script>

<style lang="scss">
  * {
    margin: 0;
  }

  body {
    background-color: #9abfee;
  }

  .filler-box {
    background: #3a4c34;
    height: 800px;
  }

  p {
    color: #fff;
    bottom: 0;
    background-color: #3a4c34;
    text-align: right;
    padding: 10px 30px;
  }
</style>
