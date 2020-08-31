<template>
    <div class="display">{{ value }}</div>
</template>

<script>
export default {
    name: 'Display',
    props: ['value']
}
</script>

<style>

.display {
    grid-column: span 4;

    display: flex;
    justify-content: center;
    align-items: center;

    font-size: 2.1rem;
}
</style>