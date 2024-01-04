<template>
  <div class="teams">
    <div v-for="teamData in state.teams" :key="teamData.id">
      <!-- Step 3:inserting the team component into the HTML where you want it. Note self-closing tag. Must add class binder for the child component to recognize it. SO>> :prop being passed down=objectData/value being passed down. It is getting passed as an attribute on a component tag  -->
      <team :teamProp="teamData" />
    </div>
  </div>
</template>

<script>
import { reactive } from 'vue';
// step one: import the Team component 
import Team from './components/Team.vue';

export default {
  setup() {
    const state = reactive({
      teams: [{
        id: "1a",
        name: "Red Team",
        score: 0,
      }, {
        id: "2a",
        name: "Blue Team",
        score: 0,
      }, {
        id: "3a",
        name: "Yellow Team",
        score: 0,
      }, {
        id: "4a",
        name: "Green Team",
        score: 0,
      }]
    })
    return {
      state
    }
  },
  // step two: add component you want injected outside of the setup
  components: {
    Team
  }
}
</script>
<style >
.teams {
  display: flex;
  justify-content: center;
  margin: 8px
}
</style>
