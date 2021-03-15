<template>
  <div class="question-box-container">
    <b-jumbotron>
      <template #lead>
        {{ questions.question }}
      </template>

      <hr class="my-4" />

      <p>
        List of answers
      </p>

      <b-button variant="primary" href="#">Do Something</b-button>
      <b-button variant="success" href="#">Do Something Else</b-button>
    </b-jumbotron>
  </div>
</template>

<script>
export default {
    props: [
        'questions'
    ],
};
</script>

<style>
</style>