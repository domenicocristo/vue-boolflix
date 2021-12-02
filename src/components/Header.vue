<template>
  <header>
    <img src="../assets/logo.png" alt="logo">
    <div>
      <input type="text" placeholder="Search Movies" v-model="inputText">
      <button @click.prevent="$emit('search', inputText)">Search</button>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      inputText: "",
    }
  },
}
</script>

<style scoped lang="scss">
header {
  height: 100px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #000;
  img {
    margin-left: 50px;
  }
  input {
    padding: 10px 15px;
    margin-right: 5px;
  }
  button {
    margin-right: 50px;
    padding: 12px 15px;
    color: #fff;
    background-color: #e50914;
    border: none;
    border-radius: 2px;
    cursor: pointer;
  }
}
</style>