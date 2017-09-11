<template>
  <div>
    <app-header v-bind:title="title" v-on:changeTitle="updateTitle($event)"></app-header>
    <app-heroes v-bind:heroes="heroes"></app-heroes>
    <app-footer v-bind:title="title"></app-footer>
    <form-Helper>
      <!-- <h2 slot="title">{{title}}</h2>
      <p slot="text">I am the paragraph for the slot</p> -->
      <div slot="form-header">
        <h3>This is the title of form</h3>
        <p>Information about form</p>
      </div>
      <div slot="form-fields">
        <input type="text" placeholder="name" required/>
        <input type="password" placeholder="password" required/>
      </div>
      <div slot="form-controls">
        <button v-on:click="handleSubmit">Submit</button>
      </div>
    </form-Helper>
    <hr/>
    <keep-alive>
      <component v-bind:is="component"></component>
    </keep-alive>
    <button v-on:click="component='form-one'">Go to form-one</button>
    <button v-on:click="component='form-two'">Go to form-two</button>
    <hr/>
    //Add blog
    <add-Blog></add-Blog>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Heroes from './components/Heroes.vue';
import formHelper from './components/formHelper.vue';
import formOne from './components/form-one.vue';
import formTwo from './components/form-two.vue';
import addBlog from './components/addBlog.vue';


export default {
  components: {
    'app-header': Header,
    'app-footer': Footer,
    'app-heroes': Heroes,
    'form-Helper': formHelper,
    'form-one': formOne,
    'form-two': formTwo,
    'add-Blog': addBlog
  },
  data () {
    return {
      heroes: [
          {name: 'GuanYu', speciality: 'VueJS Expert', show: false},
          {name: 'ZhangFei', speciality: 'ReactJS Expert', show: false},
          {name: 'CaoYun', speciality: 'AngularJS Expert', show: false},
          {name: 'MaCao', speciality: 'D3JS Expert', show: false},
          {name: 'HuangCong', speciality: 'NodeJS Expert', show: false},
          {name: 'LiuBi', speciality: 'Project Manager', show: false}
      ],
      title: "Vue Heroes",
      component: 'form-one'
    }
  },
  methods: {
    updateTitle: function(updatedTitle) {
      this.title = updatedTitle;
    }
  }
}
</script>
