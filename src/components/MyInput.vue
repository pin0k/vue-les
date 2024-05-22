<template>
  <input 
    type="text" 
    class="search"
    v-model="searchText"
  >
</template>

<script>
export default {
  name: 'MyInput'
}
</script>

<style>
  input {
    height: 25px;
    margin-left: 40px;
  }
</style>
