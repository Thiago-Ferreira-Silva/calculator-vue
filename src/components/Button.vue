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

.button.operation {
    background-color: #fa8231;
    color: #fff;
}

.button.operation:active {
    background-color: #fa8231cc;
}

.button {
    font-size: 1.4rem;
    background-color: #f0f0f0;
    border: none;
    border-bottom: solid 1px #888;
    border-right: solid 1px #888;
    outline: none;
}

.button:active {
    background-color: #ccc;
}

</style>