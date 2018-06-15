<template>
  <div id="app">
    <ul class="day-list">
      <li v-for="dayObj in days" v-bind:key="dayObj.key">
        <Day v-bind:dayTitle="dayObj.day"></Day>
      </li>
    </ul>
  </div>
</template>

<script>
import Day from './components/Day.vue'

export default {
  name: 'app',
  data(){
    return {
      days: [{day: 'Sun', key: 0},
              {day: 'Mon', key:1},
              {day: 'Tue', key:2},
              {day: 'Wed', key:3},
              {day: 'Thu', key:4},
              {day: 'Fri', key:5},
              {day: 'Sat', key: 6}]
    }
  },
  components: {
    Day
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.day-list {
  list-style-type: none;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-evenly;
  padding: 0;
}
.day-list li {
  padding: .5em;
}
</style>
