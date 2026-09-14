<script setup>
import { ref } from 'vue'
const items = ref(['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'])
const newItem = ref('')

// TODO: Add Code Here
function addItem() {
    const item = newItem.value.trim()

    if (item) {
        items.value.push(item)
        newItem.value = ''
    }
}

function removeItem(index) {
    items.value.splice(index, 1)
}

</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
    <input v-model="newItem" type="text" placeholder="Enter an item">
    <button @click="addItem">Add!</button>

    <ul>
        <li v-for="(item, index) in items" :key="index">
            {{ item }}
            <button @click="removeItem(index)">Delete</button>
        </li>
    </ul>
</template>
