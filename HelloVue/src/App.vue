<script setup lang="ts">
import {ref} from "vue"

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
</script>

<template>
  <h1>ちわーっす {{ name }} くん</h1>
  いま {{ timeRef }} だよ
</template>