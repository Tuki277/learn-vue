<template>
  <div class="list-user">
      <p>List</p>
      <User 
        v-bind:key="user.id"
        v-for="user in listUser"
        v-bind:user="user"
        v-on:deleteUser="deleteUser"
      />
  </div>
</template>

<script>

import User from './User'

export default {
    name: 'ListUser',
    components: {
        User
    },
    props: [ 'listUser' ],
    methods: {
      deleteUser(data) {
        console.log('delete user trong list vue ', data)
        this.$emit('deleteUserEvent', data)
      }
    }
}
</script>

<style>

</style>