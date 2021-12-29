<template>
  <div class="container pt-1">
    <div class="card">
      <h2>Актуальные новости {{ now }}</h2>
    </div>
    <app-news></app-news>
    <app-news></app-news>
  </div>
</template>

<script>
import AppNews from './AppNews'
export default {
  name: 'App',
  data () {
    return {
      isOpen: false,
      now: new Date().toLocaleDateString(),
      news: [
        'Джо Байден победил на выборах в США',
        'Vue 3 успешно работает'
      ]
    }
  },
  components: {
    // 'app-news': AppNews
    // AppNews: AppNews
    AppNews
  }
}
</script>

<style lang="scss">

</style>
