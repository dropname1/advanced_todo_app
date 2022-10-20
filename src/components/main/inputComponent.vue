<template>
  <div class="inputWrapper">
    <input type="text">
  </div>
</template>

<script>
export default {
data () {
  return {
  }
},
methods: {
}
}
</script>

<style scoped>
.inputWrapper {
    margin: 0 auto;
    width: 90%;
}
.inputWrapper input {
    width: 100%;
    height: 58px;
    box-sizing: border-box;
    background-color: #2B2E38;
    outline: none;
    border: none;
    border-radius: 20px;
    padding-left: 20px;
    color: white;
    font-size: 18px;
    margin-top: 20px;
    box-shadow: 1px 1px 5px rgb(14, 14, 14);
}
</style>