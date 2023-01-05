<script setup lang="ts">
import {ref, computed, reactive} from "vue"

const name = ref("Ino Junsuke")

const timeRef = ref("");
setInterval(
  (): void => {
    const newTime = new Date();
    const newTimeStr = newTime.toLocaleTimeString();
    timeRef.value = newTimeStr;
  },
  1000
);

const data = reactive({
  pi: Math.PI,
  radius: 1,
});
//const PI = ref(Math.PI);
//const radius = ref(1);
const area = computed(
  (): number => {
    return data.radius * data.radius * data.pi;
  }
);

setInterval((): void => {
    data.radius = Math.round(Math.random() * 10);
  }, 
  2000
);
</script>

<template>
  <p><h1>ちわーっす {{ name }} くん</h1></p><br>
  <p><h2> いま {{ timeRef }} だよ</h2></p>
  <p><h2>半径 {{ data.radius }} の円の面積は {{ area }} です。<br>(π={{ data.pi }})</h2></p>
</template>