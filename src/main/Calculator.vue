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
            displayValue: 0,
            clearDisplay: false,
            operation: null,
            values: [0, 0],
            current: 0
        }
    },
    methods: {
        clearMemory() {
            Object.assign(this.$data, this.$options.data())
        },
        setOperation(operation) {
            if(this.current === 0) {
                this.operation = operation
                this.current = 1
                this.clearDisplay = true
            } else {
                let result = 0
                switch (this.operation) {
                    case '+' :
                        result = this.values[0] + this.values[1]
                        break
                    case '-' :
                        result = this.values[0] - this.values[1]
                        break
                    case '*' :
                        result = this.values[0] * this.values[1]
                        break
                    case '/' :
                        result = this.values[0] / this.values[1]
                        break
                }

                this.values = [result, 0]
                this.current = 1
                this.clearDisplay = true
                this.displayValue = result

                if (operation === '=') {
                        this.current = 0
                        this.clearDisplay = false
                        this.operation = null
                } else {
                    this.operation = operation
                }
            }
        },
        addDigit() {
            //faça sem olhar
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