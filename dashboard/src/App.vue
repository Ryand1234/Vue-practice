<template>
  <div id="app">
    <div class="columns">
      <div class="column has-background-primary  is-one-fifth">
          <div id="search">
            <input type="text" id="location-input" ref="input" placeholder="Your Location" @key.enter="organizingDetails">
            <button id="search-btn" @click="organizingDetails">
              <img alt="Vue logo" src="./assets/submit.svg">
            </button>
          </div>
        <div id="info" class="mt-6 pt-4">
          <div class="wrapper-left">
            <div id="current-weather" class="is-size-1-desktop">
              <p> <span class="has-text-weight-bold is-text-size-3">
                {{currentWeather.temp}}
              </span>*C</p>
            </div>
            <div id="weather-desc" class="has-text-weight-bold">
              {{currentWeather.summary}}
            </div>
            <div class="columns mt-2">
              <div class="column">
                <div id="min-detail">
                  <span>Low: </span>
                  {{currentWeather.todayHighLow.todayTempLow}}
                  <span>*C</span>
                </div>
                <div>at {{currentWeather.todayHighLow.todayTempLowTime}}</div>
              </div>
              <div class="column">
                <div id="max-detail">
                  <span>High: </span>
                  {{currentWeather.todayHighLow.todayTempHigh}}
                  <span>*C</span>
                </div>
                <div>at {{currentWeather.todayHighLow.todayTempHighTime}}</div>
              </div>
            </div>
            <div class="mt-6 pt-3">
              {{currentWeather.dayTime.day}}, {{currentWeather.dayTime.date}}, {{currentWeather.dayTime.time}} 
            </div>
            <div class="mt-3 has-text-left ml-5">
              <div class="has-text-weight-bold">
                {{currentWeather.location.place}}
              </div>
              <div>
                Lat: {{currentWeather.location.lat}}
              </div>
              <div>
                Long: {{currentWeather.location.lng}}
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
          },
          dayTime: {
            day: "Thu",
            date: "Dec 24, 2020",
            time: "04:21 AM"
          },
          location: {
            lat: "40.174*N",
            lng: "74.001 *W",
            place: "New Delhi, India"
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
