<template>
  <div id="app">
    <app-all-user></app-all-user>
    <br><hr><br>
    <app-add-user></app-add-user>


  </div>
</template>

<script>
import AddUser from './components/AddUser.vue';
import AllUser from './components/AllUser.vue';
export default {
  components :{
    AppAllUser : AllUser,
    AppAddUser : AddUser
  },
}
</script>

<style>

</style>
