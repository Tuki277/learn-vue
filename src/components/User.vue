<template>
  <div class="User">
      <p>{{ user.email }}</p>
      <button
        class="delete"
        v-on:click="handleDelete"
      >
        Delete
      </button>
  </div>
</template>

<script>
export default {
    name: 'User',
    props: [
      'user'
    ],
    methods: {
      handleDelete () {
        var data = {id: this.user.id }
        this.$emit('deleteUser', data)
      }
    }
}
</script>

<style>

</style>