<template>
    <section class="calculator__keyboard" >
      <Numbers @numberClicked="figure => emitFigure(figure)"/>
      <Operations/>
    </section>
</template>

<script>
import Numbers from "./Numbers.vue";
import Operations from "./Operations.vue";
export default {
   name: 'Keyboard',
   components: {
    Numbers,
    Operations
   },
   methods: {
    emitFigure(number) {
      this.$emit('numberClicked', number);
    },
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
}

</style>

