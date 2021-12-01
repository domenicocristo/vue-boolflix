<template>
  <div id="app">
    <Header @search="searching"/>

    <Main/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data() {
    return {
      inputText: "",
      searchText: "",
    }
  },
  methods: {
    searching(text) {
      this.searchText = text;
      console.log(this.searchText)
    }
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Avenir, Helvetica;
}
</style>