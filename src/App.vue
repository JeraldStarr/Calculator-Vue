<template>
  <div class="calculator">
    <section class="calculator__display">
        100
    </section>
    <section class="calculator__keyboard">
      <div class="calculator__numbers">
        <div class="calculator__number">1</div>
        <div class="calculator__number">2</div>
        <div class="calculator__number">3</div>
        <div class="calculator__number">4</div>
        <div class="calculator__number">5</div>
        <div class="calculator__number">6</div>
        <div class="calculator__number">7</div>
        <div class="calculator__number">8</div>
        <div class="calculator__number">9</div>
        <div class="calculator__number">0</div>
        <div class="calculator__number">,</div>
      </div>
      <div class="calculator__operations">
        <div class="calculator__addition calculator__operation">+</div>
        <div class="calculator__substraction calculator__operation">-</div>
        <div class="calculator__divistion calculator__operation">/</div>
        <div class="calculator__multiplication calculator__operation">x</div>
      </div>
    </section>
  </div>
</template>

<script>

export default {
  name: 'App',
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
      font-size: 100px;
    }
    &__keyboard {
      display: flex;
      width: 100%;
      padding: 8px;
    }
    &__numbers {
      display: grid;
      grid-template-columns: 120px 120px 120px;
      row-gap: 20px;
    }
    &__number {
      width: 100px;
      height: 50px;
      line-height: 50px;
      text-align: center;
      border: 1px solid $border-color;
      border-radius: 2px;
      font-size: 30px;
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
