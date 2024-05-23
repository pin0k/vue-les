<template>
  <div>
    <UserForm/>
  </div>
  <div>
    <ProductList/>
  </div>
  <div>
    <PhotoEditor/>
  </div>
  <div>
    <SearchUser/>
  </div>
  <div>
    <SearchUserProto/>
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
import SearchUserProto from './components/SearchUserProto.vue';
import PhotoEditor from './components/PhotoEditor.vue';
import ProductList from './components/ProductList.vue';
import UserForm from './components/UserForm.vue';

export default {
  name: 'App',
  components: {
    MyComponents,
    MyHomeLesson1,
    UserCard,
    SearchUser,
    SearchUserProto,
    PhotoEditor,
    ProductList,
    UserForm
  }
}
</script>

<style></style>
