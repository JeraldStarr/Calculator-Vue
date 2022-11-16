<template>
    <section class="calculator__keyboard" >
      <Numbers 
        @numberClicked="figure => emitFigure(figure)"
        @sumOperation="() => sum()"
      />
      <Operations 
        :figure=figure 
        @addition="factor=>emitAddition(factor)"
        @subtraction="factor=>emitSubtraction(factor)"
      />
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
   props: {
    figure: String,
   },
   methods: {
    emitFigure(number) {
      this.$emit('numberClicked', number);
    },
    emitAddition(factor) {
      this.$emit("addition", factor);
    },
    emitSubtraction(factor) {
      this.$emit("subtraction", factor);
    },
    sum() {
      this.$emit("sumOperation");
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
}

</style>

