<template>
  <div class="table-questions_question">
    <div class="question">
      {{ question.labels.fr }}
    </div>
    <div class="score-container">
      <div class="score" v-for="score in scores" :key="score.filter_id">
        <span
          :class="{
            bad: score.value < 25,
            ok: score.value > 25 && score.value < 65,
            good: score.value > 65,
          }"
        >
          {{ score.value.toFixed(1) }}
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    question: Object,
    scores: Array,
  },
}
</script>

<style lang="scss" scoped>
@import "./../../assets/scores";
.table {
  &-questions {
    &_question {
      border-bottom: 1px solid $border;
      display: flex;
      height: 60px;
      &:nth-child(even) {
        background: #fafafa;
      }
    }
  }
}
.question {
  width: 30vw;
  padding: 12px;
  border-right: 1px solid $border;
  flex: none;
}

.score-container {
  display: flex;
}

.score {
  width: 115px;
  flex: none;
  border-right: 1px solid $border;
  display: flex;
  justify-content: center;
  align-items: center;
  > span {
    padding: 8px;
    background: rgba($border, 0.4);
    color: black;
    font-weight: bold;
    font-size: 0.7rem;
    border-radius: 5px;
    &.bad {
      background: $score_1_light;
      color: $score_1_dark;
    }
    &.ok {
      background: $score_5_light;
      color: $score_5_dark;
    }
    &.good {
      background: $score_9_light;
      color: $score_9_dark;
    }
  }
}
</style>
