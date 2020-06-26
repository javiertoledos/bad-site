<template>
  <div class="home">
    <LeakReferrer msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import LeakReferrer from '@/components/LeakReferrer.vue'

export default {
  name: 'Home',
  components: {
    LeakReferrer
  }
}
</script>
