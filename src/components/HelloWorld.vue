<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input v-model="username" placeholder="Username">
  </div>
  <dir>
    <input v-model="password" placeholder="Password">
  </dir>
  <div id="example-1">
    <button v-on:click="fetchToken(username, password)">Submit</button>
  </div>
</template>

<script>

import axios from 'axios'

export default {
  name: 'HelloWorld',
  username: "null",
  password: "null",
  props: {
    msg: String
  },
  el: '#example-1',
  data: function() {
    return 0;
  },
  methods: {
    fetchToken(username, password){
      axios.get('http://ec2-44-204-141-35.compute-1.amazonaws.com:3200/users/sign-in/'+username+'/'+password).then(response => {
        console.log(response)
      })
    },
  }
}
</script>

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
