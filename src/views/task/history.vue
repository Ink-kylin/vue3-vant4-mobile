<script setup lang="ts" name="HistoryPage">
  import LineChart from '@/views/task/lineChart.vue';
  import PieChart from "@/views/task/pieChart.vue";
  import { ref } from 'vue';

  const onClickLeft = () => history.back();
  const list = ref([]);
  const loading = ref(false);
  const finished = ref(false);

  const onLoad = () => {
    // 异步更新数据
    // setTimeout 仅做示例，真实场景中一般为 ajax 请求
    setTimeout(() => {
      for (let i = 0; i < 10; i++) {
        list.value.push(list.value.length + 1);
      }

      // 加载状态结束
      loading.value = false;

      // 数据全部加载完成
      if (list.value.length >= 40) {
        finished.value = true;
      }
    }, 1000);
  };
</script>
<template>
  <div>
    <van-nav-bar
      title="历史作业"
      left-text="返回"
      left-arrow
      @click-left="onClickLeft"
    />
    <van-tabs v-model:active="activeName">
      <van-tab title="图表" name="a">
        <line-chart />
        <pie-chart />
      </van-tab>
      <van-tab title="列表" name="b">
        <van-list
          v-model:loading="loading"
          :finished="finished"
          finished-text="没有更多了"
          @load="onLoad"
        >
          <van-cell v-for="item in list" :key="item" :title="item" />
        </van-list>

      </van-tab>
    </van-tabs>




  </div>
</template>
<style scoped></style>
