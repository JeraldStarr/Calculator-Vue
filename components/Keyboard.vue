<template>
    <section class="calculator__keyboard" >
      <Numbers @keyClicked="figure => displayFigure(figure)"/>
      <div class="calculator__operations">
        <div class="calculator__addition calculator__operation">+</div>
        <div class="calculator__substraction calculator__operation">-</div>
        <div class="calculator__divistion calculator__operation">/</div>
        <div class="calculator__multiplication calculator__operation">x</div>
      </div>
    </section>
</template>

<script>
import Numbers from "./Numbers.vue";
export default {
   name: 'Keyboard',
   components: {
    Numbers,
   },
   methods: {
    displayFigure(figure) {
      this.number = figure;
      console.log(this.number);
      this.number = figure;
      alert(this.number);
    },
    test() {
      alert("test")
    }
   },
   data() {
    return {
      number: null
    }
   },
}
</script>

<style lang="scss" scoped>
$border-color: #000;
.calculator {
    &__keyboard {
      display: flex;
      width: 100%;
      padding: 8px;
    }
    &__operations {
      display: grid;
      grid-template-columns: 120px;
      row-gap: 20px;
    }
    &__operation {
      width: 120px;
      height: 50px;
      line-height: 50px;
      text-align: center;
      border: 1px solid $border-color;
      border-radius: 2px;
      font-size: 30px;
    }
}

</style>

