<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <div  id="show">
    <div v-if="show">
      <div class="card-body">
        <ul class="list-inline">
          <li v-for="item in items" :key="item" class="list-inline-item">
            {{item.counter}}
            <btn :label="item.title" v-on:click="console.log('hehs')" />
          </li>
        </ul>
      </div>
    </div>
    <div>
      <button @mouseover="show=true" @mouseleave="show=false">like</button>
    </div>
    </div>
    
  </div>
</template>

<script>
import btn from "@/components/Button.vue";
export default {
  name: "App",
  components: {
    btn,
  },
  data() {
    return {
      show: false,
      items: [
        { id: 1, title: "like", counter: 0 },
        { id: 2, title: "love", counter: 0 },
        { id: 4, title: "haha", counter: 0 },
        { id: 5, title: "wow", counter: 0 },
        { id: 6, title: "angry", counter: 0 },
      ],
    };
  },
};
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
#show{
  display: grid;
  align-items: center;
  justify-items: center;
  
}

#show > * {
  grid-area:1/1/1/1;

}
</style>
