<template>
  <nav class="container">
    <HelloWorld :state="state">
        <template v-slot:top class="games">
          <h3>游戏分类</h3>
          <ul>
            <li v-for="(item, index) in state.games" :key="index">{{ item }}</li>
          </ul>
        </template>
        <template v-slot:bottom><a href="#">更多游戏>>></a></template>
    </HelloWorld>
    <HelloWorld>
      <div slot="top" class="movies">
        <h3>电影分类</h3>
        <ul>
          <li v-for="(item, index) in state.movies" :key="index">{{ item }}</li>
        </ul>
      </div>
      <a slot="bottom" href="#">更多电影>>></a>
    </HelloWorld>
    <HelloWorld>
      <div slot="top" class="musics">
        <h3>音乐分类</h3>
        <ul>
          <li v-for="(item, index) in state.musics" :key="index">{{ item }}</li>
        </ul>
      </div>
      <a slot="bottom" href="#">更多音乐>>></a>
    </HelloWorld>
  </nav>
</template>

<script lang="ts">
import { defineComponent } from "vue"
import HelloWorld from "./components/HelloWorld.vue";
export default defineComponent({
  setup() {
    const state = {
      games: ["王者荣耀", "刺激战场", "第五人格", "永劫无间"],
      movies: ["成龙历险记", "刺激战场", "宝贝计划", "黑客帝国"],
      musics: ["光年之外", "浪人琵琶", "答案", "回忆总想哭"],
    };
    return {
      state
    };
  },
  components: { HelloWorld }
})

</script>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.games {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}

nav {
  padding: 30px;
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
