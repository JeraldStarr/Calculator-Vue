<template>
  <div class="calculator">
    <section class="calculator__display">

    </section>
    <section class="calculator__keyboard">
      <div class="numbers"></div>
      <div class="operation">
        <div class="addition">+</div>
        <div class="substraction">-</div>
        <div class="divistion">/</div>
        <div class="multiplication">x</div>
      </div>
    </section>
  </div>
</template>

<script>

export default {
  name: 'App',
}
</script>

<style>
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
  }
  .calculator {
    display: flex;
    flex-direction: column;
    width: 500px;
    height: 700px;
    border: 1px solid blue;
  }

  .calculator__display {
    width: 100%;
    height: 40px;
    border: 1px solid gray;
  }
  .calculator__keyboard {
    width: 100%;
    flex-grow: 1;
    border: 1px solid red;
  }

</style>
