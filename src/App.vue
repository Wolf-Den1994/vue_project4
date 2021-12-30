<template>
  <div class="container pt-1">
    <div class="card">
      <h2>Динамические и асинхронные компоненты</h2>
      <app-button :color="active === 'one' ? 'primary' : ''" @action="active = 'one'">One</app-button>
      <app-button :color="active === 'two' ? 'primary' : ''" @action="active = 'two'">Two</app-button>
    </div>

<!--    <app-text-one v-if="active === 'one'"></app-text-one>-->
<!--    <app-text-two v-else-if="active === 'two'"></app-text-two>-->

    <component :is="componentName"></component>
  </div>
</template>

<script>
import AppButton from './AppButton'
import AppTextOne from './AppTextOne'
import AppTextTwo from './AppTextTwo'
export default {
  data () {
    return {
      active: 'one' // two
    }
  },
  components: {
    AppButton,
    AppTextOne,
    AppTextTwo
  },
  computed: {
    componentName () {
      // if (this.active === 'one') {
      //   return 'app-text-one'
      // }
      // return 'app-text-two'
      return 'app-text-' + this.active
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
