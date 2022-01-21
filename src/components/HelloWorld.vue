<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input type="text" v-model="emailReceiver" placeholder="Email Receiver" />
    <br />
    <input type="text" v-model="emailBody" placeholder="Email Message" />
    <br />
    <button v-on:click="postEmail">Send Email</button>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data: function () {
    return {
      emailReceiver: null,
      emailBody: null,
      response: null,
    };
  },
  methods: {
    postEmail: function () {
      axios.post("http://192.168.64.15:8080/", {
        receiver: this.emailReceiver,
        body: this.emailBody,
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
