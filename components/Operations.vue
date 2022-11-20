<template>
    <div class="calculator__operations">
        <div 
            class="calculator__addition calculator__operation" 
            @click=add
        >+</div>
        <div class="calculator__substraction calculator__operation" @click=subtraction>-</div>
        <div class="calculator__division calculator__operation" @click=division>/</div>
        <div class="calculator__multiplication calculator__operation" @click=multiplication>x</div>
    </div>
</template>

<script>

export default {
    name: 'Operations',
    props: {
        figure: String,
    },
    methods: {
        add() {
            this.$emit("addition", parseInt(this.figure));
        },
        division() {
            this.$emit("division", parseInt(this.figure));
        },
        subtraction() {
            this.$emit("subtraction", parseInt(this.figure));
        },
        multiplication() {
            this.$emit("multiplication", parseInt(this.figure));
        },
    }
}
</script>

<style scoped lang="scss">
    $border-color: #000;
.calculator {
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
      cursor: pointer;
    }
}
</style>
