<template>
  <div>
    <SearchUser/>
  </div>
  <div>
    <UserCard/>
  </div>
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
import UserCard from './components/UserCard.vue';
import SearchUser from './components/SearchUser.vue';

export default {
  name: 'App',
  components: {
    MyComponents,
    MyHomeLesson1,
    UserCard,
    SearchUser
  }
}
</script>

<style></style>
