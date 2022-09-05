<template>
  <div class="home">
    <h2>test</h2>
    <p :class="{danger: alto.vale, 'text-low': low }" >{{ number }}</p>
    <button class="btn" @click="number--" >-</button>
    <button class="btn" @click="number++">+</button>
    <MsgComp v-if="alto" :msg="alto" />
  </div>
</template>

<script>
import MsgComp from './components/MsgComp.vue'

export default {
  name: 'App',
  data() {
    return {
      number: 0,      
    }
  },
  components: {
    MsgComp
  },
  computed:{
    alto(){
      if(this.number > 3) return { 
        vale: "muy alto !", 
        style: "background-color: #b53b3b" }
      else if(this.number < 0) return { 
        vale: "muy bajo",
        style: "background-color: #4f4f87" }
    else return false
  },
  low(){
    return this.number < 0 ? true : false   
  }
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#app .btn{
  padding: 1em;
  margin: 1em;
  cursor: pointer;
  border: none;
  box-shadow: 0px 0px 3px #8080806e;
  background-color: #148057;
  color: white;
  font-size: 1.2em;
}

#app .danger{
  color: red;
  font-size: 1.4em;
}

#app .text-low{
  color: blue;
  font-size: .8em;
  background-color: #d1d1ef;
  max-width: 15px;
  margin: auto;
  padding: 7px;
}
</style>
