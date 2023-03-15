<template>
  <van-grid :gutter="10" square clickable>
    <van-grid-item icon="src/assets/icons/task.svg" text="历史作业" to="/task/history" />
    <van-grid-item icon="photo-o" text="当前作业" to="/task/inProgress" />
  </van-grid>
</template>

<script setup lang="ts" name="TaskPage">



</script>

<style scoped lang="less"></style>
