<template>
  <div id="app">
    <Header />

    <b-container class="bv-example-row">
      <b-row>
        <b-col sm="6" offset="3">
          <QuestionBox 
            v-bind:questions="questions[index]"
          />
        </b-col>
      </b-row>
    </b-container>


  </div>
</template>

<script>
import Header from './components/Header.vue'
import QuestionBox from './components/QuestionBox'

export default {
  name: 'App',
  components: {
    Header,
    QuestionBox
  },
  data () { // ngang voi state
    return {
      questions: [],
      index: 0
    }
  },
  mounted: function () {
    fetch('https://opentdb.com/api.php?amount=10&category=27&type=multiple', {
      method: 'GET'
    }).then((res) => {
      // console.log(res.json())
      return res.json()
    }).then((json) => {
      this.questions = json.results
    })
  }
}
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
