<template>
  <div class="calculator">
  <Display :figure=figure />
  <Keyboard
    :figure=figure
    @numberClicked="figure => handleFigure(figure)"
    @addition="factor => add(factor)"
    @subtraction="factor => subtract(factor)"
    @division="factor => divide(factor)"
    @multiplication="factor => multiple(factor)"
    @sumOperation="() => sum()"

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
          factor: '',
          displayReset: false,
          operationType: null,
    }
  },
  methods: {
    handleFigure(value) {
      this.updateFigure(value)
    },
    updateFigure(value) {
      if (this.displayReset) {
        this.figure = '';
        this.restorDisplayReset();
      }
      this.figure += value;
    },
    add(factor) {
      this.factor = factor;
      this.displayReset = true;
      this.operationType = "addition";
    },
    subtract(factor) {
      this.factor = factor;
      this.displayReset = true;
      this.operationType = "subtraction";
    },
    divide(factor) {
      this.factor = factor;
      this.displayReset = true;
      this.operationType = "division";
    },
    multiple(factor) {
      this.factor = factor;
      this.displayReset = true;
      this.operationType = "multiplication";
    },
    sum() {
      switch(this.operationType) {
        case "addition":
        this.figure = (parseInt(this.figure) + parseInt(this.factor)).toString();
        console.log(typeof this.figure);
        break;
        case "subtraction":
        this.figure = (parseInt(this.factor)- parseInt(this.figure)).toString();
        break;
        case "division":
        this.figure = (parseInt(this.factor) / parseInt(this.figure)).toString();
        break;
        case "multiplication":
          console.log("mnożenie")
        this.figure = (parseInt(this.factor) *  parseInt(this.figure)).toString();
        break;

      }
      
      this.restorDisplayReset();
    },
    restorDisplayReset() {
      this.displayReset = !this.displayReset;
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
