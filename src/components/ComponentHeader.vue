<template>
  <header>
      <h1>
          {{ text }}
          <br>
          {{ titleHeader }}
          <br>
          <button v-on:click="changeTitleHeader">Thay doi title tu ComponentHeader</button>
      </h1>
  </header>
</template>

<script>
export default {
    name: 'ComponentHeader',
    data () {
        return {
            text: 'Header'
        }
    },
    props: [
        'titleHeader'
    ],
    methods: {
        changeTitleHeader () {
            // khong duoc phep thay doi truc tiep props tu component cha
            // -> truyen su kien thong bao ra ben ngoai
            // -> kich hoat su kien 'changeTitleEvent' trong commHeader.vue
            // -> khi kich hoat func ngoai App.vue nó sẽ chạy
            // -> khi func chạy -> thay đổi dữ liệu
            console.log('trc khi thay doi su kien')
            var data = {
                title : 'Thay doi header tu comp Header'
            }
            this.$emit('changeTitleEvent', data)
            console.log('sau khi thay doi su kien')
        }
    }
}
</script>

<style>

</style>