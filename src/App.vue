<template>
  <div id="app">
    <button 
      v-on:click="title = 'Thay doi title' "
    >
      Thay doi title tu component
    </button>
    <ComponentHeader 
      v-bind:titleHeader="title"
      v-on:changeTitleEvent="handleChangeTitle"
    />
    <img src="./assets/logo.png" />
    <h1>{{ msg }}</h1>
    <ListUser 
      v-bind:listUser="listUser"
      v-on:deleteUserEvent="handleDeleteUser"
    />
    <ComponentFooter v-bind:titleFooter="title"/>
    <Demoref />
  </div>
</template>

<script>

import ComponentHeader from './components/ComponentHeader'
import ComponentFooter from './components/ComponentFooter'
import ListUser from './components/ListUser'
import Demoref from './components/DemoRef'

export default {
  name: 'App',
  data () {
    return {
      msg: 'Hello Vue JS',
      title: 'Hello Vue Header',
      listUser: [
        { id: 1, email: 'Email1@gmail.com', active: true },
        { id: 2, email: 'Email2@gmail.com', active: false },
        { id: 3, email: 'Email3@gmail.com', active: true },
        { id: 4, email: 'Email4@gmail.com', active: false },
        { id: 5, email: 'Email5@gmail.com', active: true },
      ]
    }
  },
  components: {
    ComponentHeader,
    ComponentFooter,
    ListUser,
    Demoref
  },
  methods: {
    handleChangeTitle(data) {
      this.title = data.title
      console.log('change title app.vue ')
    },
    handleDeleteUser(data) {
      var index = -1
      this.listUser.forEach((user, idx) => {
        if(user.id === data.id) {
          index = idx
        }
      })
      if (index !== -1) {
        this.listUser.splice(index, 1)
      }
      console.log('app.vue ', data)
    }
  }
}

</script>

<style>
#app {
  text-align: center;
  margin-top: 60px;
  color: #2c3e50;
}
</style>
