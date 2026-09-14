<script setup>
import { ref, computed } from 'vue'

const x = ref(0)
const y = ref(0)
const operators = ref(["+", "-", "*", "/", "%"])
const selectedOp = ref("+")

// TODO: Add Code Here
// Note: DO NOT USE "eval()". In security, "eval" is considered "evil"!!!
const result = computed(() => {
    switch (selectedOp.value) {
        case "+":
            return x.value + y.value
        case "-":
            return x.value - y.value
        case "*":
            return x.value * y.value
        case "/":
            return y.value === 0 ? "Cannot divide by zero" : x.value / y.value
        case "%":
            return y.value === 0 ? "Cannot divide by zero" : x.value % y.value
        default:
            return "Invalid operator"
    }
})

    
</script>

<template>
    <div class="calculator">
        <p>x <input v-model.number="x"></p>
        <p>
            <select v-model="selectedOp">
                <option v-for="op in operators">{{ op }}</option>
            </select>
        </p>
        <p>y <input v-model.number="y"></p>

        <p>---------------------</p>

        <p>= {{ result }}</p>
    </div>
</template>

<style scoped>
p,
input {
    font-family: monospace;
}

p {
    white-space: pre;
}

.calculator {
    width: fit-content;
    margin: 0 auto;
    text-align: center;
}
</style>
