<template>
    <div class="calculator">
        <Display :value="displayValue" />
        <Button label="AC" triple @on-click="clearMemory"/>
        <Button label="/" operation @on-click="setOperation"/>
        <Button label="7" @on-click="addDigit"/>
        <Button label="8" @on-click="addDigit"/>
        <Button label="9" @on-click="addDigit"/>
        <Button label="*" operation @on-click="setOperation"/>
        <Button label="4" @on-click="addDigit"/>
        <Button label="5" @on-click="addDigit"/>
        <Button label="6" @on-click="addDigit"/>
        <Button label="-" operation @on-click="setOperation"/>
        <Button label="1" @on-click="addDigit"/>
        <Button label="2" @on-click="addDigit"/>
        <Button label="3" @on-click="addDigit"/>
        <Button label="+" operation @on-click="setOperation"/>
        <Button label="0" double @on-click="addDigit"/>
        <Button label="." @on-click="addDigit"/>
        <Button label="=" operation @on-click="setOperation"/>
    </div>
</template>

<script>
import Button from '../components/Button'
import Display from '../components/Display'

export default {
    name: 'Calculator',
    components: { Button, Display },
    data: function() {
        return {
            displayValue: '0',
            clearDisplay: false,
            operation: null,
            values: [0, 0],
            current: 0
        }
    },
    methods: {
        clearMemory() {

        },
        setOperation() {

        },
        addDigit() {

        }
    }
}
</script>

<style>

.calculator {
    height: 320px;
    width: 235px;
    border-radius: 5px;
    overflow: hidden;

    display: grid;
    grid-template-columns: repeat(4,25%);
    grid-template-rows: 1fr repeat(5,48px);
}

</style>