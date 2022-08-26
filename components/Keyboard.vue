<template>
    <section class="calculator__keyboard">
      <Numbers/>
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
   }
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

