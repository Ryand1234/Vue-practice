<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <div class="columns">
      <div class="column has-background-primary  is-one-fifth">
          <div id="search">
            <input type="text" id="location-input" ref="input" placeholder="Your Location" @key.enter="organizingDetails">
            <button id="search-btn" @click="organizingDetails">
              <img alt="Vue logo" src="./assets/submit.svg">
            </button>
          </div>
        <div id="info">
          <div class="wrapper-left">
            <div id="current-weather">
              {{currentWeather.temp}}
              <span>*C</span>
            </div>
            <div id="weather-desc">
              {{currentWeather.summary}}
            </div>
            <div class="temp-max-min">
              <div class="max-desc">
                <div id="max-detail">
                  <i>^</i>
                  {{currentWeather.todayHighLow.todayTempHigh}}
                  <span>*C</span>
                </div>
                <div>at {{currentWeather.todayHighLow.todayTempHighTime}}</div>
              </div>
              <div class="min-desc">
                <div id="min-detail">
                  <i>^</i>
                  {{currentWeather.todayHighLow.todayTempLow}}
                  <span>*C</span>
                </div>
                <div>at {{currentWeather.todayHighLow.todayTempLowTime}}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="column">
        <Content :highlights="highlights" ></Content>
      </div>
    </div>
  </div>
</template>

<script>
import Content from './components/Content.vue'
export default {
  name: 'App',
  components: {
    'Content': Content
  },
  data() {
    return {
      filename: "App.vue",
      currentWeather: {
          temp: "40",
          summary: "Nice Weather",
          todayHighLow: {
            todayTempHigh: "42",
            todayTempLow: "26",
            todayTempHighTime: "03:00 pm",
            todayTempLowTime: "04:50 am"
          }
        },
        highlights: {
          uvindex: "3",
          windstatus: {
            speed: "20 km/h",
            direction: "N-E"
          },
          visibility: "12 km",
        },
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
