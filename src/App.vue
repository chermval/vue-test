<template>
  <div id="app">
      <h2>Test vue-cli + jsonplaceholder User LIST </h2>
     
      <div v-for="user in usersList" >
        <user-card  v-bind:name="user.name"
          v-bind:email="user.email"
          v-bind:website="user.website">
        </user-card> 
      </div>
          
  </div>
</template>

<script>
import axios from 'axios'
import UserCard from './components/UserCard'

export default {
    name: 'App',
   components: { UserCard },
    data: function () {
      return {
        usersList: []
      }
    },
    methods: {
      fetchUserList: function () {
        axios.get('https://jsonplaceholder.typicode.com/users').then((response) => {
          this.usersList = response.data
        }, (error) => {
          console.log(error)
        })
      }
    },
    mounted: function () {
      this.fetchUserList()
    }
  }


</script>

<style>
#app {
  color: #2c3e50;
}
</style>
