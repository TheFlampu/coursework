<template>
  <label :for="key">{{ option.text }}
    <input
        type="checkbox"
        :id="key"
        :value="option"
        v-model="checked"
        @change="$emit('update:modelValue', this.isChecked)"
    >
  </label>
  <br>
</template>

<script>
export default {
  data: () => ({
    isChecked: false
  }),
  computed: {
    checked: {
      get() {
        return this.modelValue
      },
      set(val) {
        this.isChecked = val
      }
    }
  },
  props: ['option', 'key', 'modelValue'],
  name: "OptionItem",
  }
</script>

<style>

</style>