<template>
  <div id="app">

    <div>
      <ul>
        <li v-for="(log,i) in this.logs" :key="i">
          {{log}}
        </li>
      </ul>
    </div>

    <div v-if="this.messages.length>0">
    <hr>
      <ul>
        <li>
          <span v-for="(msg,i) in this.messages" :key="i" v-on:click="messages.splice(i,1)">
          {{msg}}
          </span>
        </li>
      </ul>
      <input type="button" value="送信" @click="this.sendMessage" >
    </div>
<hr>
    <Palette v-on:push="pushWord" />
  </div>
</template>

<script>
import Palette from './components/Palette.vue'
export default {
  name: 'app',
  components: {
    Palette
  },
  data:()=>{return {
    messages:[],
    logs:[]
  }},
  methods: {
    pushWord(msg){
      this.messages.push(msg);
    },
    sendMessage(){
      this.logs.push(this.messages.join(""));
      this.messages = [];
    }
  },

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
