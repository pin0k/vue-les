<template>
  <div class="flex">
    <input 
      type="text" 
      class="search"
      v-model="searchText"
    >
    <button
      @click="$emit('search', searchText)"
    >
      Найти
    </button>
  </div>
</template>

<script>
export default {
  name: 'MyInput',
  data() {
    return {
      searchText: ''
    }
  }
}
</script>

<style scoped>
  .flex {
    display: flex;
    align-items: baseline;
  }
  input {
    height: 25px;
    margin-left: 40px;
  }
</style>
