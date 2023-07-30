<script setup lang="ts">
import {useSlots} from "vue";

const slots = useSlots()
</script>

<template>
  <div class="quiz">
    <div class="quiz-title">
      <div v-if="slots.number" class="quiz-number">
        <slot name="number"/>
      </div>
      <slot name="title"/>
    </div>
    <div class="quiz-desc">
      <slot name="desc"/>
    </div>
    <div class="quiz-content">
      <slot name="content"/>
    </div>
  </div>
</template>

<style scoped lang="less">
.quiz {
  display: flex;
  flex-direction: column;
  gap: .5rem;
  border-radius: 5px;
  background: rgba(0, 0, 0, .05);
  padding: 1rem;
  margin: .5rem 0;
}

.quiz-title {
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
  gap: 1rem;
  font-size: 1.3rem;
  font-weight: 500;
}

.quiz-number {
  background: #2196f3;
  color: white;
  width: 28px;
  height: 28px;
  border-radius: 100%;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  line-height: 1;
}

.quiz-desc {
  color: rgba(0, 0, 0, .6);
  line-height: 1.5;
}
</style>