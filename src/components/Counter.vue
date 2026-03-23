<script setup>
import { ref, defineEmits} from 'vue';

const emit = defineEmits(['increment',"decrement"])

</script>
<template>
    <div class="counter">
        <button class="counter-btn" @click="emit('increment')">+</button>    
        <button class="counter-btn" @click="emit('decrement')">-</button>    
    </div>
</template>
<style>
.counter-btn{
    background-color: lightseagreen;
    border: none;
    font-size: 40px;
}
</style>