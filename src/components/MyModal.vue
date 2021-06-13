<template>
  <div
    v-if="isModal"
    id="overlay"
  >
    <div id="content">
      <p><slot /></p>
      <p>
        <button
          @click="emitTurnOff"
        >
          close
        </button>
      </p>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Emit, Vue } from 'vue-property-decorator'

@Component({
  name: 'MyModal'
})
export default class extends Vue {
  @Prop()
  private isModal!: boolean

  @Emit('from-child')
  emitTurnOff (): void {
    // Emit the particular event
  }
}
</script>

<style lang="scss" scoped>
#overlay {
  z-index: 1;

  /*画面全体を覆う設定*/
  position:fixed;
  top:0;
  left:0;
  width:100%;
  height:100%;
  background-color:rgba(0,0,0,0.5);

  /*画面の中央に要素を表示させる設定*/
  display: flex;
  align-items: center;
  justify-content: center;
}

#content{
  z-index:2;
  width:50%;
  padding: 1em;
  background:#fff;
}

</style>
