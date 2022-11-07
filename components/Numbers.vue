<template>
    <div class="calculator__numbers">
        <div class="calculator__number" 
            v-for="i in 10" 
            v-bind:key="i"
            @click="emitFigure(`${i}`)"
        >
        {{displayKeyLabel(i)}}
        </div>
        <div class="calculator__number calculator__equal"
            @click="sum"
        >
            {{"="}}
        </div>
    </div>
</template>

<script>
export default {
    name: "Numbers",
    methods: {
        emitFigure(number) {
            this.$emit('numberClicked', this.displayKeyLabel(number));
        },
        displayKeyLabel(i) {
            i = parseInt(i);
            if (i === 10) {
                return 0;
            } else return i;
        },
        sum() {
            this.$emit("sumOperation");
        }
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