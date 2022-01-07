<template>
  <label :for="uuid" v-if="label">{{ label }}</label>
  <input
    :placeholder="label"
    class="field"
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
    v-bind="$attrs"
    :id="uuid"
  />
</template>
<script>
import UniqueID from '@/features/UniqueID.js'
export default {
  props: {
    label: {
      type: String,
      default: '',
    },
    modelValue: {
      type: [String, Number],
      default: '',
    },
  },
  setup() {
    const uuid = UniqueID().getID()
    return {
      uuid,
    }
  },
}
</script>

<style></style>
