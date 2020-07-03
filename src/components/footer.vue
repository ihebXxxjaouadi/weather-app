<template>
  <div class="footer-component">
    <footer>
      <p>&copy; this app made it by IHEB</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: "footer"
};
</script>

<style scoped>
.footer-component {
  position: absolute;
  bottom: 0px;
  height: 20px;
  width: 100%;
  background-color: #f1f1f1;
}

footer p {
  color: gray;
  text-align: center;
  font-weight: bold;
  font-family: Arial, Helvetica, sans-serif;
}
</style>
