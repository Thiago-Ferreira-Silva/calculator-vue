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
    justify-content: flex-start;
    align-items: center;
    padding: 5px;

    background-color: #0004;
    font-size: 2.1rem;
    overflow: hidden;
}
</style>