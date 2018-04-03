<template>
  <div id="app"> 
    <div class="container">
      <Pineapple v-bind:class="`mouth-${count}`"/>
      <h1>{{ title }}</h1>
      <div>
        <div class="button-container">
          <a href="#" class="button" v-on:click.prevent="decreaseCount()">-</a>
          <h2>{{ count }} serving(s)</h2>
          <a href="#" class="button" v-on:click.prevent="increaseCount()">+</a>
        </div>
        <input type="range"  min="0" max="5" v-model="count"/>
      </div>
    </div>
  </div>
</template>

<script>
import Pineapple from './assets/img/pineapple.svg';
import 'normalize.css';

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
  },
  methods: {
    increaseCount: function() {
      if (this.count < 5) {
        this.count++;
      }
    },
    decreaseCount: function () {
      if (this.count > 0) {
        this.count--;
      }
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
  padding: 0 30px 30px;
  display: flex;
  justify-content: center;
}

.container {
  max-width: 900px;
  width: 100%;
};

input[type="range"] { 
  -webkit-appearance: none;
  width: 100%;
  height: 15px;
  background-color: #83c190;
  border: 1px solid darken(#83c190, 4%);
  border-radius: 10px;
  transition: all 0.3s ease;
  width: 100%;
  outline: 0;
}

input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none;
  cursor: pointer;
  width: 45px;
  height: 45px;
  background-color: #f1e6b8;
  border-radius: 45px;
  box-shadow: 0px 0px 3px darken(#f1e6b8, 15%);
  transition: all 0.5s ease;
}

.button-container {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  margin: 30px 0;
  text-align: center;
}

.button {
  -webkit-appearance: none;
  transition: all 0.5s ease;
  background-color: #83c190;
  border-radius: 60px;
  border: 0;
  outline: 0;
  box-shadow: 0px 0px 7px rgba(0, 0, 0, 0.4);
  color: #f1e6b8;
  cursor: pointer;
  min-width: 60px;
  height: 60px;
  font-size: 30px;
  position: relative;
  margin: 0 40px;
  display: inline-block;
  text-decoration: none;
  line-height: 60px;

  &:hover {
    background-color: darken(#83c190, 8%);
  }

  &:active {
    box-shadow: 0px 0px 3px rgba(0, 0, 0, 0.5);
    top: 1px;
    left: 1px;
  }
}

h1, h2 {
  font-family: 'Domine', Georgia, serif;
}
</style>
