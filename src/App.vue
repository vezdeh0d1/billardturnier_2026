<template>
  <div class="app">
    <Navigation />
    <Rules />
    <GroupStage />
    <Playoff />
    <Teams />
  </div>
</template>

<script>
import Navigation from "./components/Navigation.vue";
import Rules from "./views/Rules.vue";
import GroupStage from "./views/GroupStage.vue";
import Playoff from "./views/Playoff.vue";
import Teams from "./views/Teams.vue";

export default {
  name: "App",
  components: {
    Navigation,
    Rules,
    GroupStage,
    Playoff,
    Teams,
  },
};
</script>
