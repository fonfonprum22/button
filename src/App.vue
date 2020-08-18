<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
          <ul>
          <li v-for="item in items" :key="item.id" class="list-inline-item">
            <btn 
              :label="item.title"
              @onCounter = "onCounter"
              />
            {{item.counter}}
          </li>
        </ul>
        score : {{items[0].counter + (items[1].counter * 10) + (items[2].counter * 5) + (items[3].counter * 20) + (items[4].counter * (-5)) + (items[5].counter * (-50))}}
    </div>
</template>

<script>
import btn from "@/components/Button.vue";
export default {
  name: "App",
  components: {
    btn,
  },
  methods : {
    onCounter(value){
      if (value == 'like') {
        this.items[0].counter++
      }
      else if (value == 'love'){
        this.items[1].counter++
      }
      else if(value == 'haha'){
        this.items[2].counter++
      }
      else if (value == 'wow'){
        this.items[3].counter++
      }
      else if (value == 'sad'){
        this.items[4].counter++
      }
      else if (value == 'angry'){
        this.items[5].counter++
      }
    }
  },
  data() {
    return {
      items: [
        { title: "like", counter:0},
        { title: "love", counter:0},
        { title: "haha", counter:0},
        { title: "wow", counter:0},
        { title: "sad", counter:0},
        { title: "angry", counter:0},
      ],
    };
  }
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
</style>
