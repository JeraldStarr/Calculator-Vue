<template>
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
</template>

<script>
export default {
    name: "Numbers",
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