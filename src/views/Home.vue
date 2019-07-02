<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <Weather />
    <Counter />
  </div>
</template>

<script>
// @ is an alias to /src
import Counter from '@/components/Counter.vue'
import Weather from '@/components/Weather.vue'

export default {
  name: 'home',
  components: {
    Counter,
    Weather
  }
}
</script>
