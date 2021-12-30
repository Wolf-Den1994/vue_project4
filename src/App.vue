<template>
  <div class="container pt-1">
    <div class="card">
      <h2>Slots</h2>
    </div>
    <app-block>
      <p>Это текст в блоке</p>
      <template #header>
        <h3>Заголовочек</h3>
      </template>
      <template v-slot:footer>
        <hr>
        <small>ФУТЕР</small>
      </template>
    </app-block>
  </div>
</template>

<script>
import AppBlock from './AppBlock'
export default {
  components: {
    AppBlock
  }
}
</script>

<style lang="scss" scoped>

</style>
