<template>
  <div class="demo-ref">
      <h1>DemoRef</h1>
      <button
        v-on:click="handleClickInputFile"
        class="avatar"
      >
          Change avatar
      </button>
      <input 
        type="file"
        ref="fileInputAvatar"
        style="display: none"
      >
  </div>
</template>

<script>
export default {
    name: 'demo-ref',
    data() {
        return {

        }
    },
    methods: {
        handleClickInputFile() {
            this.$refs.fileInputAvatar.click()
        }
    }
}
</script>

<style>

</style>