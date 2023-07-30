<script setup lang="ts">
const props = defineProps({
  type: {
    type: String,
    default: "text"
  },
  maxlength: {
    type: Number
  },
  hint: {
    type: String
  },
  modelValue: {
    type: String
  }
})

const emit = defineEmits(["update:modelValue"])
</script>

<template>
  <div class="textfield">
    <input @change="e => emit('update:modelValue', e.target.value)" class="textfield-input" :type="type" :maxlength="maxlength"/>
    <small class="hint">{{ hint }}</small>
  </div>
</template>

<style scoped lang="less">
.textfield {
  display: flex;
  flex-direction: column;
}

.textfield-input {
  outline: none;
  width: calc(100% - .4rem);
  background: white;
  border: 2px solid rgba(0, 0, 0, .2);
  border-radius: 5px;
  padding: .4rem .2rem;
  font-size: 1rem;
  line-height: 1;
  transition: all .2s ease;

  &:hover {
    border-color: #2196F3;
  }

  &:focus {
    border-color: transparent;
    box-shadow: 0 1px 0 2px #2196F3;
  }
}
</style>