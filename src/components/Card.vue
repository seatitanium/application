<template>
  <div class="card">
    <div class="card-header">
      <div class="card-title">
        <slot name="title"/>
      </div>
      <div v-if="slots.subtitle" class="card-subtitle">
        <slot name="subtitle"/>
      </div>
    </div>
    <div class="card-content">
      <slot name="content"/>
    </div>
    <div class="card-action">
      <slot name="action"/>
    </div>
  </div>
</template>

<script lang="ts" setup>
import {useSlots} from "vue";

const slots = useSlots();
</script>

<style lang="less" scoped>
.card {
  display: block;
  border-radius: 5px;
  border: 1px solid rgba(0, 0, 0, .21);
  padding: 2rem;

  height: 650px;
  overflow-y: auto;
  width: 500px;
  position: relative;
}

.card-title {
  font-weight: 500;
  font-size: 2rem;
}

.card-subtitle {
  color: rgba(0, 0, 0, .6)
}

.card-header {
  display: flex;
  flex-direction: column;
  gap: .5rem;
}

.card {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.card-content {
  font-size: 1rem;
}

.card-action {
  position: absolute;
  bottom: 0;
  width: calc(100% - 4rem);
  display: flex;
  justify-content: center;
  padding: 2rem 0;
}
</style>