<template>
  <div class="about">
    <h1>current team: {{team.name}}</h1>
    <p>{{$store.state.sum}}</p>
    <button v-on:click="$store.state.sum++; $store.state.lastTeam = team.name">counter</button>
    <p>Last team name clicked: {{$store.state.lastTeam}}</p>
  </div>
</template>


<script>
export default {
  data() {
    return {
      teams: [
        {
          id: "c36136ef-552f-4dc9-84b6-65ecb8574e81",
          name: "Team_A",
        },
        {
          id: "ed0459f5-716d-4ef4-99ba-5dc750dfe0d0",
          name: "Team_B",
        },
        {
          id: "60d0d5d5-8ce9-41d9-a65b-13a090c10ae1",
          name: "Team_C",
        },
      ]
    };
  },
  computed: {
    team() {
      return this.teams.find(team => team.id == this.$route.params.id)
    }
  }
};
</script>