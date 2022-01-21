<template>
  <div id="app">
  <EmployeeList />
  <PostComponent />
  <Users />
  </div>
</template>

<script>
import EmployeeList from './components/EmployeeList.vue'
import PostComponent from './components/PostComponent';
import Users from './components/Users.vue'
export default {
  name: 'App',
  components: {
    EmployeeList,
    PostComponent,
    Users
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
