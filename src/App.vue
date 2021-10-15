<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import { onMounted } from "@vue/runtime-core";
import HelloWorld from "./components/HelloWorld.vue";
import G6 from "@antv/g6";

onMounted(() => {
  debugger;
  // 定义数据源
  const data = {
    // 点集
    nodes: [
      {
        id: "node1",
        x: 100,
        y: 200,
      },
      {
        id: "node2",
        x: 300,
        y: 200,
      },
    ],
    // 边集
    edges: [
      // 表示一条从 node1 节点连接到 node2 节点的边
      {
        source: "node1",
        target: "node2",
      },
    ],
  };
  // 创建 G6 图实例
  const graph = new G6.Graph({
    container: "mountNode", // 指定图画布的容器 id
    // 画布宽高
    width: 800,
    height: 500,
  });
  // 读取数据
  graph.data(data);
  // 渲染图
  graph.render();
});
</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- <HelloWorld msg="Hello Vue 3 + Vite" /> -->
  <!-- /* 图的画布容器 */ -->
  <div id="mountNode"></div>
</template>

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
