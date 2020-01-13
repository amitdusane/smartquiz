""}{
        selectedIndex: null,
        correctIndex: 0
    }
  },
  watch: {
      currentQuestion() {
          this.selectedIndex = null;
      }
  },
  methods: {
      selectedAnswer(index) {
        this.selectedIndex = index
      },
      submitAnswer() {
          let isCorrect = false
          if(this.selectedIndex === this.correctIndex){
              isCorrect = true
          }
          this.increamentCorrect(isCorrect)
      }
  },
  computed: {
    answers() {
      let answers = [...this.currentQuestion.incorrect_answers]
      answers.push(this.currentQuestion.correct_answer)
      console.log(answers.indexOf(this.currentQuestion.correct_answer))
      return _.shuffle(answers)
    },
    queIndex() {
        return this.questionIndex++
    }
  }  
};
</script>

<style scoped>
.list-group {
  margin-bottom: 15px;
}
.list-group-item:hover {
  background-color: #EEE;
  cursor: pointer;
}
.btn {
  margin: 0 5px;
}
.selected {
    background-color: lightblue
}
.correctAnswer {
    background-color: lightgreen
}
.wrongAnswer {
    background-color: red
}

</style>