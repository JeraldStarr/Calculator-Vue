<template>
    <section class="calculator__display">
        {{figure}}
    </section>
</template>

<script>
export default {
    name: 'Display',
    props: {
        figure: String
    }
}
</script>

<style lang="scss" scoped>
    $border-color: #000;
    .calculator {
        &__display {
            width: 100%;
            height: 100px;
            line-height: 100px;
            text-align: right;
            padding: 0 25px;
            border-bottom: 1px solid $border-color;
            font-size: 50px;
        }
    }

</style>