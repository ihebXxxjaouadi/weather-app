<template>
  <div id="app">
    <Header />
    <Searsh />
    <Container
      v-bind:country="country"
      v-bind:temperature="getTemperature"
      v-bind:descreption="descreption"
      v-bind:status="status"
    />
    <Footer />
  </div>
</template>

<script>
import Header from "./components/header.vue";
import Searsh from "./components/searsh.vue";
import Container from "./components/container_info";
import Footer from "./components/footer";
export default {
  name: "App",
  data() {
    return {
      cntry: "",
      country: "-",
      temperature: "-",
      descreption: "-",
      status: "",
      api_key: "4690b2c1bfa1afb3c955418fb61e58eb",
      url_base: `http://api.openweathermap.org/data/2.5/weather?q=`,
      weather: {}
    };
  },
  components: {
    Header,
    Searsh,
    Container,
    Footer
  },
  methods: {
    getWeather: function() {
      console.log("you Entred");
      console.log(
        `${this.url_base}${this.cntry}&appid=${this.api_key}&units=metric`
      );
      fetch(`${this.url_base}${this.cntry}&appid=${this.api_key}&units=metric`)
        .then(res => {
          return res.json();
        })
        .then(this.setWeather);
    },
    setWeather: function(result) {
      this.weather = result;
      console.log(this.weather);
      this.setWeatherInfo();
    },
    setWeatherInfo: function() {
      console.log("setWeatherInfo func");
      this.status = this.weather.weather[0].main;
      this.country = this.cntry;
      this.temperature = Math.round(this.weather.main.temp);
      this.descreption = this.weather.weather[0].description;
    }
  },
  computed: {
    getTemperature() {
      return `${this.temperature}°C`;
    }
  }
};
</script>

<style>
* {
  padding: 0px;
  margin: 0px;
  font-family: cursive;
}
</style>
