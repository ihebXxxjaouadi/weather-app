<template>
  <div class="our-searsh">
    <input type="text" v-model="country" placeholder="Enter City" />
    <button @click="sendData">Find City</button>
  </div>
</template>

<script>
export default {
  name: "searsh",
  data() {
    return {
      country: ""
    };
  },
  methods: {
    sendData() {
      this.$parent.cntry = this.country;
      this.$parent.getWeather();
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  text-align: center;
}

input {
  outline: none;
  border: none;
  text-align: left;
  margin-top: 80px;
  padding: 7px 10px;
  width: 300px;
  border: 1px solid #2f89fc;
  border-radius: 4px;
  color: #2f89fc;
  transition: 0.2s;
}

input::placeholder {
  color: #49beb7;
}

input:hover,
input:focus {
  padding-left: 18px;
  padding-right: 2px;
}

button {
  padding: 7px 2px;
  outline: none;
  border: none;
  background: none;
  background-color: #2f89fc;
  border: 1px solid #2f89fc;
  border-radius: 4px;
  margin-left: 1px;
  color: white;
  cursor: pointer;
}

button:hover {
  background-color: #06aae0;
  border-color: #06aae0;
}
</style>
