<template>
  <div id="app">
    <h1>Testing {{name}}</h1>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <ul>
      <li v-for="(data,index) in arr" v-bind:key="index">
        <span v-if="data%2 === 0">{{data}} {{index}}</span>
      </li>
    </ul>
    <ol>
      <li v-for="(n,index1) in evenNumbers" v-bind:key="index1">{{ n }}</li>
    </ol>
    <br />
    <span>Vue Input box style :</span>
    <input v-model="txtValue" placeholder="Type something..." />
    <p>
      Message is:
      <strong>{{ txtValue }}</strong>
    </p>
    <br />
    <!-- Radio Button example -->
    <div>
      <section>
        <h3>radio buttons</h3>
        <input type="radio" v-model="color" value="0" />red
        <input type="radio" v-model="color" value="1" />blue
        <input type="radio" v-model="color" value="2" />yellow
        <br />
        <span>value: {{color}}</span>
      </section>
    </div>

    <!-- Check Box example -->
    <div id="demo">
      <input type="checkbox" id="0" value="Manoj" v-model="checkedNames" />
      <label for="Manoj">Manoj</label>
      <input type="checkbox" id="1" value="Khaleel" v-model="checkedNames" />
      <label for="Khaleel">John</label>
      <input type="checkbox" id="2" value="Sumeet" v-model="checkedNames" />
      <label for="Sumeet">Sumeet</label>
      <br />
      <span>Checked names: {{ checkedNames }}</span>
    </div>
  </div>
</template>

<script>
export default {
  // script part
  name: "app",
  data() {
    return {
      name: "Manoj Pachuveedu",
      city: "Kochi",
      arr: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
      txtValue: "Initial Value",
      color: "",
      checkedNames: []
    };
  },
  beforeCreate() {
    // alert("Before Create method called");
  },
  created() {
    // data access
  },
  beforeMount() {
    // data + DOM about to access
  },
  mounted() {
    // data + DOM
  },
  updated() {
    //alert('changed');
  },
  beforeDestroy() {
    // can access + DOM data
  },
  destroyed() {},
  computed: {
    evenNumbers: function() {
      return this.arr.filter(function(number) {
        return number % 2 === 0;
      });
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  color: red;
}
</style>
