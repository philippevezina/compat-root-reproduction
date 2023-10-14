<script lang="ts">
import Button from './components/Button.vue'
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'App',
  components: {
    Button
  },
  data() {
    return {
      count: 0
    }
  },
  created() {
    // Here, `$on` is an an existing function on the root Vue instance with `@vue/compat` but has
    // a Typescript error because of incorrect typing: Property '$on' does not exist on type 'ComponentPublicInstance'.
    // `$root` is not actually `ComponentPublicInstance` with `@vue/compat`, but rather `LegacyPublicInstance`.
    this.$root?.$on('increment', this.increment)
  },
  methods: {
    increment() {
      this.count++
    }
  }
})
</script>

<template>
  <header>
    <div class="wrapper">
      <Button />
      {{ count }}
    </div>
  </header>
</template>
