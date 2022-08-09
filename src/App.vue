<template>
  <div id="app">
    <button @click="selectedIndex = 5">Cancel</button>
    <div class="container">
      <div
          v-for="(_, i) in range"
          :class="['item', selectedIndex == i ? 'item-select' : '', i === 2 ? 'img-middle' : i < 2 ? 'img-left' : 'img-right']"
          @click="selectedIndex = i"
      >
        <div :class="['main-text', selectedIndex == i ? 'main-text-select' : '']">
          <div class="title">Hello</div>
          <div :class="['item-text', selectedIndex == i ? 'item-text-select' : '']">
            <span style="width: 100px">他们虽然都可以做出动画效果</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import {ref} from "vue";

const selectedIndex = ref(-1);
const range = [1, 2, 3, 4, 5];
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
  height: 180px;
  width: 20%;
  margin: 0 10px;
  display: flex;
  flex-direction: row;
  align-items: flex-end;
  overflow: hidden;
  transition: all 0.65s;
}

.item-select {
  width: 65%;
}

.img-left {
  background-image: url("https://img-prod-cms-rt-microsoft-com.akamaized.net/cms/api/am/imageFileData/RE4wwtC?ver=b327");
  background-repeat: no-repeat;
  background-position: left center;
  background-size: cover;
}

.img-middle {
  background-image: url("https://img-prod-cms-rt-microsoft-com.akamaized.net/cms/api/am/imageFileData/RE4wwtC?ver=b327");
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
}

.img-right {
  background-image: url("https://img-prod-cms-rt-microsoft-com.akamaized.net/cms/api/am/imageFileData/RE4wwtC?ver=b327");
  background-repeat: no-repeat;
  background-position: right center;
  background-size: auto 100%;
}

.main-text {
  position: relative;
  bottom: -10px;
  width: 100%;
  padding: 0 20px;
  color: white;
  transition: all 0.55s;
}

.main-text-select {
  bottom: 20px;
}

.title {
  display: inline-block;
  height: 20px;
  width: 300px;
  font-size: 24px;
  margin-bottom: 10px;
}

.item-text {
  display: inline-block;
  width: 300px;
  opacity: 0;
  transition: all 0.65s;
}

.item-text-select {
  opacity: 1;
}
</style>
