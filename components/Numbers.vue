<template>
    <div class="calculator__numbers">
        <div class="calculator__number" 
            v-for="i in 10" 
            v-bind:key="i"
            @click="showKeyNumber(i)"
        >{{i === 10 ? 0 : i}}</div>
    </div>
</template>

<script>
export default {
    name: "Numbers",
    methods: {
        showKeyNumber(number) {
            number = number === 10 ? 0 : number;
            alert(number)
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
        }
    }
</style>