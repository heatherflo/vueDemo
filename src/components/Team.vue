<template>
  <div class="team">
    <h1 v-if="teamProp.score > 9" :class="{ green: teamProp.score > 9 }">{{ teamProp.name }}</h1>
    <h1 v-else="teamProp.score > 9" :class="{ red: teamProp.score <= 9 }">{{ teamProp.name }}</h1>
    <h3>Score: {{ teamProp.score }}</h3>
    <button :disabled="teamProp.score > 9" @click="addPoint()">+{{ teamProp.score }}</button>
    <h3 v-if="teamProp.score > 9">You're the winner!</h3>
    <h3 v-else="teamProp.score">You're a loser!</h3>
  </div>
</template>

<script>
export default {
  //step four: make a props value with the name of the prop you are passing down in the app.vue
  props: ['teamProp'], //the data we are passing down from the parent to the child are inside an array - the prop name we have given it. App.vue is our parent and Team.vue is our child. We are EXPORTING the prop into the parent - as the child component so it can read it 
  setup(props) {

    return {
      addPoint() {
        props.teamProp.score++
        //pulls the property teamProp off the props value and accesses the score
      }
    }
  }
}
</script>

<style>
.team {
  justify-content: center;
  margin: 1em
}

.green {
  color: green
}

.red {
  color: red
}
</style>