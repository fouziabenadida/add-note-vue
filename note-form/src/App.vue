<template>
  <div id="app">
  <header-top></header-top>
  <form-vue></form-vue>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Form from './components/Form.vue'

export default {
  name: 'App',
  components: {
   'header-top': Header,
   'form-vue': Form

  }
}
</script>

<style>

</style>
