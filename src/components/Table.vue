<template>
  <div class="table">
    <div class="table-countries">
      <Search />
      <Countries
        :country="filter"
        v-for="filter in filters"
        :key="filter._id"
      />
    </div>
    <div class="table-questions">
      <Questions
        :question="question"
        :scores="
          scores.find((score) => score.question_id === question._id).scores[0]
        "
        v-for="question in questions"
        :key="question._id"
      />
    </div>
  </div>
</template>

<script>
import Search from "./table/Search.vue"
import Questions from "./table/Questions.vue"
import Countries from "./table/Countries.vue"

export default {
  components: {
    Search,
    Questions,
    Countries,
  },
  props: {
    filters: Array,
    questions: Array,
    scores: Array,
  },
}
</script>

<style lang="scss" scoped>
@import "./../assets/scores";
.table {
  color: #52616e;
  display: grid;
  &-questions {
    border-top: 1px solid $border;
  }
  &-countries {
    display: flex;
  }
}
</style>
