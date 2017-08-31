<template>
  <div id="app">
<component-a></component-a>
    <ul>
      <li v-for="item in list">{{item.name +'-'+item.price}}</li>
    </ul>
    <component-a :dataA="dataA"></component-a>
    <a  :href="link">to baidu</a>
    <tr></tr>
    <a v-bind:class="className" v-bind:style="linkCss">t0000o baidu</a>
    <tr></tr>
    <button v-on:click="addItem">addItem</button>

    <a v-if="isPartA">partA</a>
    <a v-else>no data</a>
    <a v-show="!isPartA">partB</a>
    <button v-on:click="toggle">toggle</button>



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
      link : 'http://www.baidu.com',
      classA:'hello',
      classB:'heloo2',
      isPartA: true,
      linkCss:{
        'color':'red',
        'font-size':'30px'
      },
      className:{
        'red-front':true,
        'blue-front':false
      },
      dataA : 12,

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
      },
      toggle(){
        this.isPartA =!this.isPartA
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
