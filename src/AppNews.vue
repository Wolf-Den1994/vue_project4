<template>
  <div class="card">
    <h3>{{ title }}</h3>
    <button class="btn" @click="changeOpen">Открыть</button>
    <p v-if="isOpen">Lorem ipsum dolor sit amet, consectetur adipisicing elit. A, alias aliquid cum dolorem, dolores dolorum et exercitationem facere inventore minus molestiae porro quo rem sapiente similique sint tempora tempore voluptates?</p>
  </div>
</template>

<script>
export default {
  data () {
    return {
      item: 'item string'
    }
  },
  methods: {
    changeOpen (e) {
      this.isOpen = !this.isOpen
      // ESLint: Unexpected mutation of "isOpen" prop.(vue/no-mutating-props)
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
        console.log(value)
        return value === true || value === false
      }
    }
  }
}
</script>
