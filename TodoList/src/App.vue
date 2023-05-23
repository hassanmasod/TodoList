<template>
  <FirstPage />
  <HelloWorld/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import FirstPage from './components/FirstPage.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    FirstPage,
    
  }
}
</script>

<style>

</style>
