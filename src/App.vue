<template>
  <div class="calculator">
  <Display :figure=figure />
  <Keyboard
    :figure=figure
    @numberClicked="figure => handleFigure(figure)"
    @dialedFactor="factor => sum(factor)"
  />
  </div>
</template>

<script>
import Keyboard from '../components/Keyboard.vue'
import Display from '../components/Display.vue'
export default {
  name: 'App',
  components: {
    Keyboard,
    Display,
  },
  data() {
    return {
          figure: '',
    }
  },
  methods: {
    handleFigure(value) {
      this.updateFigure(value)
    },
    updateFigure(value) {
      this.figure += value;
    },
    sum(factor) {
      console.log(factor);
    }
  }
}
</script>

<style lang="scss">
  $border-color: #000;
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100vw;
    height: 100vh;
    font-family: Arial, sans-serif;
  }
  .calculator {
    display: flex;
    flex-direction: column;
    width: 500px;
    border: 1px solid $border-color;
    border-radius: 2px;
  }




</style>
