<template>
  <div>
    <h1>{{ msg }}</h1>
    <button v-on:click="postPing">Send Ping Get</button>
    <br />
    {{ info }}
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "Ping",
  data: function () {
    return {
      //response: null,
      msg: "",
      info: null,
    };
  },
  methods: {
    postPing: function () {
      axios.get("http://192.168.64.15:8080/ping").then((response) => {
        this.info = response.data;
        console.log(response.status);
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
