<template>
  <div>
    <h1>Ninjas</h1>
    <ul>
      <li v-for="ninja in ninjas">{{ninja}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data () {
    return {
      ninjas: ['Leo', 'Mika', 'Don']
    }
  }
}
</script>

<style scoped>
h1 {
  color: green;
}
</style>
