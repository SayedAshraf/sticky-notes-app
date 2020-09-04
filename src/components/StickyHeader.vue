<template>
  <div class="sticky-header">
    <b-container class="text-center">
      <h1>Sticky Notes</h1>
    </b-container>
  </div>
</template>

<script>
export default {
  name: "StickyHeader",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.sticky-header {
  background-color: #269393;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 150px;
  h1 {
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    color: #fff;
    font-size: 50px;
  }
}
</style>
