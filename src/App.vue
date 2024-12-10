<template>
  <n-space>
    <n-button type="error" size="tiny">
    <template #icon>
      <CursorClick20Regular/>
    </template>
    <span>
      click
    </span>

    </n-button>

    <h1>{{ str }}</h1>

    <n-input v-model:value="str" placeholder="enter your name"></n-input>

  </n-space>
    <button @click="toggleBox">Click</button>
    <div class="box" :style="isToggle ? 'background:lime' : 'background:red'">
      box element
    </div>
</template>

<script setup lang="ts">
import { ref, reactive, nextTick } from 'vue'
import { NButton, NInput } from 'naive-ui'
import { CursorClick20Regular } from '@vicons/fluent'

const str=ref<string>("hi");

const handleClick=(s:string)=>{
  str.value=s
}

const isToggle = ref<boolean>(false)

const toggleBox = () => {
  isToggle.value = !isToggle.value

  // await nextTick();

  // let box= document.querySelector('.box');

  // box.style.background='lime';
}
</script>

<style scoped>
.box {
  height: 100px;
  width: 100px;
  background-color: red;
  transition: background-color 1s;
  color: #ffff;
  place-content: center;
  text-align: center;
  border-radius: 12px;
  margin-top: 10px;
}
</style>
