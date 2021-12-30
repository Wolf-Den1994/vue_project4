<template>
  <div class="container pt-1">
    <div class="card">
      <h2>Актуальные новости {{ now }}</h2>
      <span>Открыто: {{ openRate }}</span>
    </div>
    <app-news
      v-for="item in news"
      :key="item.id"
      :title="item.title"
      :id="item.id"
      :isOpen="item.isOpen"
    ></app-news>
  </div>
</template>

<script>
import AppNews from './AppNews'
export default {
  name: 'App',
  data () {
    return {
      now: new Date().toLocaleDateString(),
      openRate: 0,
      news: [
        {
          title: 'Джо Байден победил на выборах в США',
          id: 1,
          isOpen: false
        },
        {
          title: 'Vue 3 успешно работает',
          id: 2,
          isOpen: false
        }
      ]
    }
  },
  components: {
    AppNews
  }
}
</script>

<style lang="scss">

</style>
