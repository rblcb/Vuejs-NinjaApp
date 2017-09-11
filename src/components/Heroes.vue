<template>
    <div id="heroes">
        <ul>
            <li v-for="hero in heroes" v-on:click="hero.show = !hero.show">
                <h2>{{ hero.name }}</h2>
                <h3 v-show="hero.show">{{ hero.speciality }}</h3>
            </li>
        </ul>
        <button v-on:click="deleteHeroes()">Delete Heroes</button>
    </div>
</template>
<script>
export default {
  props: {
    heroes:{
      type: Array,
      required: true
    }
  },
    data(){
        return{

        }
    },
    methods: {
      deleteHeroes:function() {
        this.heroes.pop();
      }
    },
    //lifecyle hooks
    // beforeCreate() {
    //   //do something before creating vue instance
    //   alert('beforeCreate');
    // },
    // created() {
    //   //do something after creating vue instance
    //   alert('created');
    // },
    // beforeMount() {
    //   //do something before mounting vue instance
    //   alert('beforeMount');
    // },
    // mounted() {
    //   //do something after mounting vue instance
    //   alert('mounted');
    // },
    // beforeUpdate() {
    //   //do something before updating vue instance
    //   alert('beforeUpdate');
    // },
    // updated() {
    //   //do something after updating vue instance
    //   alert('updated');
    // }
}
</script>
<style scoped>
#heroes{
    width: 100%;
    max-width: 1200px;
    margin: 40px auto;
    padding: 0 20px;
    box-sizing: border-box;
}
ul{
    display: flex;
    flex-wrap: wrap;
    list-style-type: none;
    padding: 0;
}
li{
    flex-grow: 1;
    flex-basis: 300px;
    text-align: center;
    padding: 30px;
    border: 1px solid #222;
    margin: 10px;
}
</style>
