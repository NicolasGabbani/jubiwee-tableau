<template>
  <div id="app">
    <Table :filters="filters" :questions="questions" :scores="scores" />
  </div>
</template>

<script>
import filters from "./json/filters"
import questions from "./json/questions"
import scores from "./json/scores"

import Table from "./components/Table.vue"

export default {
  name: "App",
  data() {
    return {
      filters,
      questions,
      scores,
    }
  },
  components: {
    Table,
  },
}
</script>

<style lang="scss" src="@/assets/app.scss"></style>
