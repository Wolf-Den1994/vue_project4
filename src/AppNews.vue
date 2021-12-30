<template>
  <div class="card">
    <h3>{{ title }}</h3>
    <button class="btn" @click="changeOpen">
      {{ isNewsOpen ? 'Закрыть' : 'Открыть' }}
    </button>
    <p v-if="isNewsOpen">Lorem ipsum dolor sit amet, consectetur adipisicing elit. A, alias aliquid cum dolorem, dolores dolorum et exercitationem facere inventore minus molestiae porro quo rem sapiente similique sint tempora tempore voluptates?</p>
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
    }
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
  }
}
</script>
