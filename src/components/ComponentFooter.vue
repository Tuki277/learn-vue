<template>
  <Footer>
      <h1>
          {{ textFooter }}
          <br>
          {{ titleFooter }}
      </h1>
  </Footer>
</template>

<script>
export default {
    name: 'ComponentFooter',
    data () {
        return {
            textFooter: 'Hello Footer'
        }
    },
    props: [
        'titleFooter'
    ]
}
</script>

<style>

</style>