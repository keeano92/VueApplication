<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      <a href="/#/Login">Login</a>
    </p>
    <p>RESULTS</p>
    <div class="results" v-if="results">
      {{ results }}
      <img :src="results.avatar_url">
      <h2>{{ results.name }}</h2>
      <div>{{ results.bio }}</div>
      <div>{{ results.location }}</div>
    </div>
  </div>
</template>

<script>
  import axios from 'axios';

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Your Current Weather',
      results: null,
      name: ""
    }
  },
  created() {
      let self = this;

      axios.get('https://api.github.com/users/keeano92')
              .then(response => {
        // JSON responses are automatically parsed.
        self.results = response.data
    })
      .catch(e => {
        this.errors.push(e)
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
