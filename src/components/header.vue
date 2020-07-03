<template>
  <div id="our-header">
    <h2>{{ info }}</h2>
  </div>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      info: "How is the weather in your country?"
    };
  }
};
</script>

<style scoped>
#our-header {
  height: 100px;
  background-color: #28c7fa;
  text-align: left;
  display: flex;
  align-items: center;
}

h2 {
  margin-left: 200px;
  color: white;
}
</style>
