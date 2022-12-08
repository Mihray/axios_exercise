<template>
  <div class="hello" @click="boxclick">
    HelloWorld
    <span>{{info}}</span>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HelloWorld',
  props: {
  },
  data(){
    return{
      info:null,
      form:{
                userName:'',
                password:'',
            },
    }
  },
  methods:{
    boxclick(){
      axios.get('/mtapi/mihray/randomWeather')
      .then(res=>{
              console.log(res.data)})
        .catch((err)=>{console.log(err);}),

      axios.get('/mtapi/mihray/sayHello')
      .then(res=>{
              console.log(res.data)})
        .catch((err)=>{console.log(err);}),
          axios.post('/mtapi/mihray/login')
          .then(res=>{
              console.log(res.data)
          })
          .catch((err)=>{console.log(err);});
        }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello{
  width:200px;
  height:200px;
  background-color: blue;
}
</style>
