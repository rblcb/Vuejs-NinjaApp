<template>
  <div>
    <h1>{{title}}</h1>
    <p>{{greeting()}}</p>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      title: 'Hello VueJS'
    }
  },
  methods: {
    greeting: function() {
      return 'Hi Ding';
    }
  }
}
</script>
