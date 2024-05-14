<template> 
  <div>
    <MyHomeLesson1/>
  </div>
  <div>
    <MyComponents/>
  </div>
</template>

<script>
import MyComponents from './components/MyComponents.vue';
import MyHomeLesson1 from './components/MyHomeLesson1.vue';

export default {
  name: 'App',
  components: {
    MyComponents,
    MyHomeLesson1
  }
}
</script>

<style></style>
