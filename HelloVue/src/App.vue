<script setup lang="ts">
import {ref, computed} from "vue"

const name = ref("Ino Junsuke")
const now = new Date();
const nowStr = now.toLocaleTimeString();
const timeRef = ref(nowStr);

function updateTime(): void {
  const newTime = new Date();
  const newTimeStr = newTime.toLocaleTimeString();
  timeRef.value = newTimeStr;
}

setInterval(updateTime, 1000);

const PI = ref(Math.PI);
const radius = ref(1);
const area = computed(
  (): number => {
    return radius.value * radius.value * PI.value;
  }
);

setInterval((): void => {
    radius.value = Math.round(Math.random() * 10);
  }, 
  2000
);
</script>

<template>
  <p><h1>ちわーっす {{ name }} くん</h1></p><br>
  <p><h2> いま {{ timeRef }} だよ</h2></p>
  <p><h2>半径 {{ radius }} の円の面積は {{ area }} です。</h2></p>
</template>