<template>
  <div id="app">
<component-a></component-a>
    <ul>
      <li v-for="item in list">{{item.name +'-'+item.price}}</li>
    </ul>
    <button v-on:click="addItem">addItem</button>

    <p v-html="hello"></p>
    <p v-text="hello"></p>
    {{hello}}
    {{status ? 'success':'fail'}}
  </div>
</template>

<script>
  import  Vue from 'vue'
  import  componentA from './components/a.vue'
  export default {
    components:{componentA},
  data(){
    return {
      hello: '<span><img>worldddd</span>',
      num : 1,
      status :true,
      list:[
        {
          name: 'apple',
          price: 34444
        },
        {
          name: 'banana',
          price: 3489
        }
      ],
      objList: {
        name :'apple',
        price: 34,
        color:'red',
        weight:'75'
      }
    }
  },
    methods:{
      addItem () {
        Vue.set(this.list,1,{
          name: 'MYCCC',
          price: "123456789"
        })
      }
    }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
