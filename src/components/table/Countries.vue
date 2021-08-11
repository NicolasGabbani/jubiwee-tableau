<template>
  <div class="table-countries_country">
    {{ country.fr }}
  </div>
</template>

<script>
export default {
  props: {
    country: Object,
  },
}
</script>

<style lang="scss" scoped>
@import "./../../assets/scores";
.table {
  &-countries {
    &_country {
      height: 100px;
      display: flex;
      flex: none;
      justify-content: center;
      align-items: center;
      padding: 12px;
      width: 115px;
      border-right: 1px solid $border;
      font-size: 0.8rem;
    }
  }
}
</style>
