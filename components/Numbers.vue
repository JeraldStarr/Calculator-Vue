<template>
    <div class="calculator__numbers">
        <div class="calculator__number" 
            v-for="i in 11" 
            v-bind:key="i"
            @click="emitFigure(`${i}`)"
        >
        {{displayKeyLabel(i, "display")}}
        </div>
    </div>
</template>

<script>
export default {
    name: "Numbers",
    methods: {
        emitFigure(number) {
            this.$emit('numberClicked', this.displayKeyLabel(number, "emit"));
        },
        displayKeyLabel(i, destiny) {
            i = parseInt(i);
            if (i === 10) {
                return 0;
            } else if (i === 11) {
                return destiny === "emit" ? "" : '=';
            } else return i;
        },
    }
}
</script>

<style lang="scss" scoped>
    $border-color: #000;
    .calculator {
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
        cursor: pointer;
        }
    }
</style>