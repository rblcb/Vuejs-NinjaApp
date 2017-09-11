<template>
  <header>
    <h1 v-on:click="changeTitle">{{title}}</h1>
  </header>
</template>

<script>

import {bus} from '../main';

export default {
  props: {
    title: {
      type: String,
      required: true
    }
  },
  data () {
    return {
      title: 'Hero Apps'
    }
  },
  methods: {
    changeTitle: function() {
    //  this.title = "Title changed"
    //  this.$emit('changeTitle', 'Title changed')
      this.title = "Title changed";
      bus.$emit('changeTitle','Title changed');
    }
  }
}
</script>

<style scoped>
header {
  background: lightgreen;
  padding: 20px;
}
h1 {
  color: #222;
  text-align: center;
}
</style>
