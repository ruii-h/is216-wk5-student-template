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


    <ul>
        <li v-for="(item, key, index) in items" :key="key">
            {{ item }}
            <button @click="removeItem(key)">Delete</button>
        </li>
    </ul>
    <input v-model="newItem" type="text" placeholder="Enter an item" @keyup.enter="addItem">
    <button @click="addItem">Add!</button>
</template>
