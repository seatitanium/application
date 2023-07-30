<script setup lang="ts">
import {useRouter} from "vue-router";

const props = defineProps({
  to: {
    required: true,
    type: String
  }
})

const router = useRouter();

function jumpto(target: string) {
  if (target.startsWith("/")) {
    router.push(target);
  } else {
    window.open(target);
  }
}
</script>

<template>
  <div class="button" @click="jumpto(to)">
    <slot/>
  </div>
</template>

<style scoped lang="less">
.button {
  background: #2196F3;
  color: white;
  padding: .4rem .8rem;
  border-radius: 5px;
  box-shadow: 0 1px 0 2px #1976d2;
  cursor: pointer;
}
</style>