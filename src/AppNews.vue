<template>
  <div class="card">
    <h3>{{ title }}</h3>
    <button class="btn" @click="changeOpen">
      {{ isNewsOpen ? 'Закрыть' : 'Открыть' }}
    </button>
    <button class="btn danger" v-if="wasRead" @click="unReadNews">
      Отметить непрочитанной
    </button>
    <div v-if="isNewsOpen">
      <hr>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. A, alias aliquid cum dolorem, dolores dolorum et exercitationem facere inventore minus molestiae porro quo rem sapiente similique sint tempora tempore voluptates?</p>
      <button v-if="!wasRead" class="btn primary" @click="readNews">Прочесть новост</button>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      isNewsOpen: this.isOpen
    }
  },
  methods: {
    changeOpen () {
      this.isNewsOpen = !this.isNewsOpen
      if (this.isNewsOpen) {
        this.$emit('open-news')
      }
    },
    readNews () {
      this.$emit('read-news', this.id)
      this.isNewsOpen = false
      this.$emit('not-read-news')
    },
    unReadNews () {
      this.$emit('un-read', this.id)
    }
  },
  props: {
    title: {
      type: String,
      required: true
    },
    id: {
      type: Number,
      required: true
    },
    isOpen: {
      type: Boolean,
      required: false,
      default: false,
      validator (value) {
        // console.log(value)
        return value === true || value === false
      }
    },
    wasRead: Boolean
  },
  // emits: ['open-news']
  emits: {
    // 'open-news' (num) { // или null
    //   if (num) {
    //     return true
    //   }
    //   console.warn('No data in open-news emit')
    //   return false
    // }
    'open-news': null,
    'read-news' (id) {
      if (id) {
        return true
      }
      console.warn('Нет параметра id для emit read-news')
      return false
    },
    'not-read-news': null,
    'un-read' (id) {
      if (id) {
        return true
      }
      console.warn('un-read emit сломан')
      return false
    }
  }
}
</script>
