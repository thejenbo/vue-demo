<template>
  <div id="app"> 
    <div>
      <Pineapple v-bind:class="`mouth-${count}`"/>
      <h1>{{ title }}</h1>
      <div>
        <input type="range"  min="0" max="5" v-model="count"/>
        <h2>{{ count }} serving(s)</h2>
      </div>
    </div>
  </div>
</template>

<script>
import Pineapple from './assets/img/pineapple.svg';

export default {
  name: 'app',
  components: {
    Pineapple,
  },
  data () {
    return {
      title: 'Did you eat your fruits and veggies today?',
      count: 0
    }
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Domine:700|Montserrat');
@import './assets/styles/pineapple.scss';

body {
  background-color: #F9CED0;
  color: #3a3a3a;
}

#app {
  font-family: 'Montserrat', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  padding: 0 30px;
  display: flex;
  justify-content: center;
  align-content: center;
}

input[type="range"] { 
  -webkit-appearance: none !important;
  width: 100%;
  height: 15px;
  background-color: #83c190;
  border: 1px solid darken(#83c190, 4%);
  border-radius: 10px;
  margin: auto;
  transition: all 0.3s ease;
  width: 500px;
  outline: 0;
}

input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none !important  ;
  width: 30px;
  height: 30px;
  background-color: #f1e6b8;
  border-radius: 30px;
  box-shadow: 0px 0px 3px darken(#f1e6b8, 15%);
  transition: all 0.5s ease;
}

.content {
  margin-top: 260px;
}

h1, h2 {
  font-family: 'Domine', Georgia, serif;
}
</style>
