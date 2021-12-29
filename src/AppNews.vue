<template>
  <div class="card">
    <h3>{{ item }}</h3>
    <button class="btn" @click="isOpen = !isOpen">Открыть</button>
    <p v-if="isOpen">Lorem ipsum dolor sit amet, consectetur adipisicing elit. A, alias aliquid cum dolorem, dolores dolorum et exercitationem facere inventore minus molestiae porro quo rem sapiente similique sint tempora tempore voluptates?</p>
  </div>
</template>

<script>
export default {
  data () {
    return {
      item: 'item string',
      isOpen: false
    }
  }
}
</script>
