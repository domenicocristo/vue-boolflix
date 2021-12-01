<template>
  <header>
    <h1>BoolfliX</h1>
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
  }
}
</script>

<style scoped lang="scss">
header {
  height: 150px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #000;
  h1 {
    color: red;
    margin-left: 50px;
  }
  input {
    margin-right: 10px;
  }
  button {
    margin-right: 50px;
    padding: 0 5px;
    cursor: pointer;
  }
}
</style>