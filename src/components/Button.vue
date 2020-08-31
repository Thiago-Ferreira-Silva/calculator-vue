<template>
    <button class="button" :class="{ operation, double, triple }" @click="$emit('on-click', label)">
        {{ label }}
    </button>
</template>

<script>
export default {
    name: 'Button',
    props: {
        label: {},
        operation: { type: Boolean },
        double: { type: Boolean },
        triple: { type: Boolean }
    }
}
</script>

<style>

.button.double {
    grid-column: span 2;
}

.button.triple {
    grid-column: span 3;
}

</style>