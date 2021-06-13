<template>
  <div>
    <!-- <button
      @click="hello"
    > -->
    <button
      @click="onClick"
    >
      <slot>Default</slot>
    </button>
  </div>
</template>

<script lang="ts">
import { Component, Emit, Vue } from 'vue-property-decorator'

@Component({
  name: 'MyButton'
})
export default class extends Vue {
  @Emit('click')
  onClick (): void {
    // Emit the click event
  }

  // private hello () {
  //   console.log('hi')
  // }
}
</script>

<style lang="scss" scoped>

</style>
