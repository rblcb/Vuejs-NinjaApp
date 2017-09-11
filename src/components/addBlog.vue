<template>
  <div id="add-blog">
    <h2>Add New Blog</h2>
    <form>
      <label>Blog title:</label>
      <input type="text" v-model.lazy="blog.title" required/>
      <label>Blog content:</label>
      <textarea v-model.lazy="blog.content"></textarea>
      <div id="checkboxes">
        <label>Hero</label>
        <input type="checkbox" value="Hero" v-model="blog.categories">
        <label>Leader</label>
        <input type="checkbox" value="Leader" v-model="blog.categories">
        <label>Chief</label>
        <input type="checkbox" value="Chief" v-model="blog.categories">
        <label>Author</label>
        <input type="checkbox" value="Author" v-model="blog.categories">
      </div>
      <label>Authors</label>
      <select v-model="blog.author">
        <option v-for="author in authors">{{author}}</option>
      </select>
    </form>
    <div id="preview">
      <h3>Preview Blog</h3>
      <p>Blog title:{{blog.title}}</p>
      <p>Blog content:</p>
      <p>{{blog.content}}</p>
      <p>Categories:</p>
      <ul>
        <li v-for="category in blog.categories">{{category}}</li>
      </ul>
      <p>Author: {{blog.author}}</p>
    </div>
  </div>
</template>

<script>

import {bus} from '../main';

export default {

  data () {
    return {
      blog: {
        title:"",
        content: "",
        categories:[],
        author:""
      },
      authors:["GuanYu", "ZhangFei", "MaCao", "HuangCong", "LiuBi"]
    }
  }
}
</script>
<style>
#add-blog *{
    box-sizing: border-box;
}
#add-blog{
    margin: 20px auto;
    max-width: 500px;
}
label{
    display: block;
    margin: 20px 0 10px;
}
input[type="text"], textarea{
    display: block;
    width: 100%;
    padding: 8px;
}
#preview{
    padding: 10px 20px;
    border: 1px dotted #ccc;
    margin: 30px 0;
}
h3{
    margin-top: 10px;
}
#checkboxes input{
  display:inline-block;
  margin-right:10px;
}
#checkboxes label{
  display: inline-block;
}
</style>
