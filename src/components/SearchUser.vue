<template>
    <h1>{{ title }}</h1>
    <h2>{{ subtitle }}</h2>
    <div>
      <label>
        Я найду тебя:
        <input 
          type="search"
          :value="searchValue"
          @input="getInputSearch"
        >
      </label>
      <button>Search</button>
    </div>
    <p>В строке поиска ввели: {{ inputSearchValue }}</p>
    <p>
      Всего имен: {{ people.length }}, совпадений: пока 0
    </p>
    <ul>
      <li
        v-for="(person, index) in people"
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
            title: 'Hello from 15.05.2024', 
            subtitle: 'Домашнее задание к 1 уроку',
            people: [
              'Иван', 'Андрей', 'Петр', 'Даниил', 'Василий', 'Дмитрий'
            ],
            inputSearchValue: ''
        }
    },
    methods: {
      getInputSearch(evt) {
        this.inputSearchValue = evt.target.value
      }
    }
  }
</script>
<style>
</style>
  