<template>
  <div class="container pt-1">
    <div class="card">
      <h2>Актуальные новости {{ now }}</h2>
    </div>
    <div class="card" v-for="item in news" :key="item">
      <h3>{{ item }}</h3>
      <button class="btn" @click="isOpen = !isOpen">Открыть</button>
      <p v-if="isOpen">Lorem ipsum dolor sit amet, consectetur adipisicing elit. A, alias aliquid cum dolorem, dolores dolorum et exercitationem facere inventore minus molestiae porro quo rem sapiente similique sint tempora tempore voluptates?</p>
    </div>
  </div>
</template>

<script>
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

  }
}
</script>

<style lang="scss">

</style>
