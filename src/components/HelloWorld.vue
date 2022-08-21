<template>
  <div class="hello">
    <!-- vue2.x写法 -->

    <!-- 默认插槽 -->
    <!-- <slot>默认插槽</slot> -->

    <!-- 具名插槽
    <slot name="top">top插槽</slot>
    <slot name="bottom">bottom插槽</slot> -->

    <!-- 作用域插槽,相当于插槽本身可以给插槽使用作用域范围内传值 -->
    <!-- <slot :data="data"></slot> -->
    <!-- 作用域插槽 子组件向父组件 传递数据 data -->
    <!-- <template v-slot="{ data }"> 我{{ data.age }}岁 -- {{ data.name }} </template> -->
    <!-- <template #default="{ data }"> 我{{ data.age }}岁 -- {{ data.name }} </template> -->
  </div>

</template>

<script lang="ts" setup>
import { defineProps } from 'vue';
defineProps({
  state: {
    type: Object,
    required: true
  }
})



</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style  lang="less">
h3 {
  margin: 40px 0 0;
}

.hello {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  justify-content: space-around;
}

ul {
  width: 200px;
  height: 300px;
  background-color: rgb(137, 137, 255);
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: center;
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
