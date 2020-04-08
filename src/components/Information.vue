<template>
  <p>
    <span>{{ name }}:</span>
    <span>{{ content }}</span>
  </p>
</template>
<script>
export default {
  name: "Information",
  props: {
    name: String,
    content: [String, Number]
  }
};
</script>
<style lang="scss" scoped>
p {
  font-size: 18px;
  padding: 20px;
  margin: 0px;
  span:first-child {
    font-weight: 600;
    margin-right: 50px;
  }
}
</style>
