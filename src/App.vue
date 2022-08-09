<template>
  <div id="app">
    <div class="container">
      <div v-for="(_, i) in range" :class="['item', selectedIndex == i ? 'item-select' : '']"
           @click="selectedIndex = i">
        <img src="https://img-prod-cms-rt-microsoft-com.akamaized.net/cms/api/am/imageFileData/RE4wwtC?ver=b327"
             alt="demo"/>
        <div :class="['main-text', selectedIndex == i ? 'main-text-select' : '']">
          <div>Hello World</div>
          <div :class="['item-text', selectedIndex == i ? 'item-text-select' : '']">
            <span style="width: 100px">他们虽然都可以做出动画效果</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import {onMounted, ref} from "vue";

const selectedIndex = ref(-1);
const range = [1, 2, 3, 4, 5];

onMounted(() => console.log("mounted this component"))
</script>

<style>
.container {
  width: 800px;
  height: 200px;
  display: flex;
  justify-content: space-around;
  align-items: center;
  border: 1px solid black;
  background-color: green;
}

.item {
  overflow: hidden;

  position: relative;
  height: 180px;
  width: 20%;
  background-color: aqua;
  margin: 0 10px;

  transition: all 0.65s;
}

.item-select {
  width: 65%;
}

img {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
}

.main-text {
  position: absolute;
  left: 30px;
  bottom: -38px;
  color: white;
  transition: all 0.55s;
}

.main-text-select {
  bottom: 10px;
}

.item-text {
  position: relative;
  display: inline-block;
  height: 10px;
  width: 100px;
  opacity: 0;
  transition: all 0.65s;
}

.item-text-select {
  /* height: 100px; */
  opacity: 1;
}
</style>
