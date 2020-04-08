<template>
  <div v-if="reviews.length > 0" class="collect-info">
    <v-card>
      <div
        v-for="({ by, quote }, index) in reviews"
        :key="index"
        class="collect-info_review"
      >
        <h3>"{{ quote }}"</h3>
        <h5>{{ by }}</h5>
      </div>
    </v-card>
  </div>
</template>
<script>
export default {
  name: "CollectInformation",
  props: {
    reviews: Array
  }
};
</script>
<style lang="scss" scoped>
.collect-info {
  &_review {
    padding: 20px;
    h3 {
      font-weight: 400;
    }
    h5 {
      text-align: right;
    }
  }
}
</style>
