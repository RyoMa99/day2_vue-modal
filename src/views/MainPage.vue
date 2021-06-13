<template>
  <div>
    <!-- clickイベントをこのコンポーネントのものだけ実施する方法。nativeでどちらも発火対象にし、captureでこのコンポーネントのものを先に実行させ、stopで止める -->
    <!-- <my-button
      @click.native.capture.stop="turnOnModal"
    > -->
    <!-- <my-button
      @click.native="turnOnModal"
    > -->
    <!-- emitを使って伝搬させる。子コンポーネント参照 -->
    <my-button
      @click="turnOnModal"
    >
      Button
    </my-button>
    <my-modal
      :is-modal="isModal"
      @from-child="turnOffModal"
    >
      slotからモーダルへ
    </my-modal>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import MyButton from '@/components/MyButton.vue'
import MyModal from '@/components/MyModal.vue'

@Component({
  name: 'MainPage',
  components: {
    MyButton,
    MyModal
  }
})
export default class extends Vue {
  private isModal = false

  turnOnModal (): void {
    this.isModal = true
    // console.log('he')
  }

  turnOffModal ():void {
    this.isModal = false
  }
}
</script>

<style lang="scss" scoped>
</style>
