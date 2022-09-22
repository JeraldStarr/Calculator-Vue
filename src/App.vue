<template>
  <div class="calculator">
    <section class="calculator__display">
        {{figure}}
    </section>
  <Keyboard @numberClicked="figure => updateFigure(figure)"/>
  </div>
</template>

<script>
import Keyboard from '../components/Keyboard.vue'
export default {
  name: 'App',
  components: {
    Keyboard,
  },
  data() {
    return {
          figure: '',
    }
  },
  methods: {
    updateFigure(value) {
      this.figure += value;
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
    &__display {
      width: 100%;
      height: 100px;
      line-height: 100px;
      text-align: right;
      padding: 0 25px;
      border-bottom: 1px solid $border-color;
      font-size: 50px;
    }
  }




</style>
