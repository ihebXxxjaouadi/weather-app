<template>
  <div id="our-container">
    <div class="weather-image">
      <img v-if="status === 'Clear'" src="../weather-icons/sun.svg" />
      <img v-else-if="status === 'Clouds'" src="../weather-icons/cloudy.png" />
      <img v-else-if="status === 'Rain'" src="../weather-icons/rainy.svg" />
      <img
        v-else-if="status === 'Thunderstorm'"
        src="../weather-icons/storm.svg"
      />
      <img v-else src="" />
    </div>
    <div class="weather-info">
      <h2 class="weather-country">{{ country }}</h2>
      <h4 class="weather-temperature">{{ temperature }}</h4>
      <p class="weather-descreption">{{ descreption }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "container",
  props: ["country", "temperature", "descreption", "status"]
};
</script>

<style>
#our-container {
  border-radius: 10px;
  box-shadow: 3px 3px 3px gray;
  background-color: rgb(250, 250, 250);
  width: 300px;
  margin: 0 auto;
  padding: 20px;
  display: grid;
  grid-template-columns: 20% auto;
  font-weight: 800;
  margin-top: 80px;
}

.weather-info {
  padding-top: 10px;
  padding-left: 70px;
}

.weather-image {
  padding-left: 20px;
}

img {
  width: 100px;
}
</style>
