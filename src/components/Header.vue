<template>
  <div>
    <b-nav tabs>
      <b-nav-item disabled><b>Smart Quiz</b></b-nav-item>
      <b-nav-item disabled>Answered {{correctAnswers}}/{{totalAnswers}}</b-nav-item>      
    </b-nav>
  </div>
</template>

<script>
export default {
    props: {
        correctAnswers: Object,
        totalAnswers: Object
    }
}
</script>