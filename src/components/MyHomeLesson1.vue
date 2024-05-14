<template>
    <div class="root">
        <h1>{{ text }}</h1>
        <p>
            Количество: 
            <button 
                type="button"
                @click="decreaseCount"
            >
                -
            </button>
            <input 
                type="number"
                :value="count"
                :min="minCount"
                :max="maxCount"
            >
            <button 
                type="button"
                @click="increaseCount"
            >
                +
            </button>
        </p>
        <p>Количество: {{ count }}</p>
    </div>
</template>

<script>
export default {
    name: 'MyComponent',
    data() {
        return {
            text: 'Hello from 14.05.2024',  
            count: '0',
            minCount: '1',
            maxCount: '10'       
        }
    },  
    methods: {
        increaseCount() {
            if(this.count < this.maxCount) {
                this.count++
            }
        },
        decreaseCount() {
            if(this.count > this.minCount) {
                this.count--
            }
        }
    }
}
</script>