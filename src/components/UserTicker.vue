<template>
  <div class="glass-card ticker-card">
    <div class="ticker-wrapper">
      <div v-for="(item, index) in tickerItems" :key="index" class="ticker-item">
        <span>{{ item.text }}</span>
        <span style="color: var(--success-color); font-weight: bold;">[生成完成]</span>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const tickerItems = ref([
  {
    "text": "用户 135****4400 创作了 BoomBap 风格 16 Bars 双押街头歌词"
  },
  {
    "text": "用户 187****9911 生成了 Trap 三连音卡点与炸裂 Punchline"
  },
  {
    "text": "用户 132****2288 完成了 Melodic Rap 浪漫情歌 Hook 旋律副歌"
  },
  {
    "text": "用户 151****6600 生成了 Hardcore 竞技 Battle 声讨歌词"
  },
  {
    "text": "用户 176****3322 取得了双押韵脚字典与卡拍吐字指导"
  }
]);
</script>
