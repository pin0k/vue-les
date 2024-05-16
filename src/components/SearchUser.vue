<template>
    <h1>{{ title }}</h1>
    <h2>{{ subtitle }}</h2>
    <div>
      <label>
        Я найду тебя:
        <input 
          type="search"
          v-on:input="inputText = $event.target.value"  
        >
      </label>
    </div>
    <p>В строке поиска ввели: {{ inputText }}</p>
    <p>
      Всего имен: {{ people.length }}, совпадений: {{ getSearch.length }}
    </p>
    <ul>
      <li
        v-for="(person, index) in getSearch"
        :key="index"
      >
        {{ person }}
    </li>
    </ul>                          
</template>
  
<script>
  export default {
    name: 'SearchUser',
    data() {
        return {
            title: 'Hello from 16.05.2024', 
            subtitle: 'Домашнее задание к 1 уроку',
            people: [
              'Иван', 'Андрей', 'Петр', 'Даниил', 'Василий', 'Дмитрий'
            ],
            inputText: ''
        }
    },
    computed: {
      getSearch() {
        return  this.people.filter(people => people.toLowerCase().includes(this.inputText.toLowerCase()));
      }
    }
  }
</script>
<style>
</style>
  