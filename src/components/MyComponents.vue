<template>
    <div class="root">
        <h1>{{ text }}</h1>
        <p>
            <label>
            Введите e-mail:
            <input 
                type="email" 
                v-bind:value="email"
                v-on:input="emailInput($event.target.value)"
            >
            </label>
        </p>
        <p>
           <label>
            Введите пароль:
            <input 
                type="password" 
                :value="password"
                @input="passwordInput"
            >
            </label>
        </p>
    </div>
</template>

<script>
export default {
    name: 'MyComponent',
    data() {
        return {
            text: 'Hello from 07.05.2024',  
            email: 'example@mail.ru',
            password: '12345678'    
        }
    },  
    methods: {
        emailInput(value) {
            this.email = value  
        },
        passwordInput(evt) {
            this.password = evt.target.value
        }
    }
}
</script>