<template>
  <h1>List</h1>
  <div class="img container">
    <div class="clothing" v-for="item in noExpenses" :key="item.id">
      <div class="card">
        <img :src="getItem(item)" class="card-img-top" :alt="item.description + ' ' + item.category">
        <div class="card-body">
          <h5 class="card-title">{{ item.category }}</h5>
          <p class="card-text">Not buying {{ item.description }} in {{ item.category }} saved you {{ item.value }} Euros!</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'noExpenses',
  data () {
    return {
      noExpenses: [
        {
          id: 1,
          category: 'Sport',
          description: 'Trainingsjacke',
          value: 30
        }
      ]
    }
  },
  methods: {
    getItem (item) {
      if (item.category === 'clothing') {
        return require('../assets/clothing.png')
      } else if (item.category === 'sport') {
        return require('../assets/sport.jpeg')
      } else if (item.category === 'tech') {
        return require('../assets/tech.jpeg')
      } else if (item.category === 'misc') {
        return require('../assets/misc.jpeg')
      }
    }
  }
}
</script>

<style scoped>
</style>
