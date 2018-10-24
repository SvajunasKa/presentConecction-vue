<template>
  <div class="table">
    <table>
      <tr>
        <th>userId</th>
        <th>id</th>
        <th>title</th>
      </tr>
      <tr  v-for="elem in data" >
        <td>{{elem.userId}}</td>
        <td>{{elem.id}}</td>
        <td>{{elem.title}}</td>
      </tr>
    </table>
  </div>
</template>

<script>
  import axios from 'axios'
export default {
  name: 'Home',
  data () {
    return {
      data: []
    }
  },
  mounted(){
    axios.get('https://jsonplaceholder.typicode.com/posts')
      .then(response =>{
        this.data = response.data;
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
