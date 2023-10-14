<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'HelloWorld',
  methods: {
    foo() {
      this.$root?.$emit('increment')
    }
  }
})
</script>

<template>
  <button @click="foo">Click Me</button>
</template>
