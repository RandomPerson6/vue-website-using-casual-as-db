<template>
  <div>
    <div v-for="item in items.items" :key="item.id">
      <h1>{{item.title}}</h1>
      <p>{{item.firstname}}</p>
      <p>{{item.surname}}</p>
      <p>{{item.address}}</p>
      <p>{{item.id}}</p>
      <p>{{item.type}}</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'HelloWorld',
  props: {
  },
  data: function() {
    return {
      items: []
    }
  },
  mounted () {
    axios.get('http://localhost:3000/items')
      .then((response) => {
        this.items = response.data
        });
  }
}
</script>

<style scoped>
</style>
