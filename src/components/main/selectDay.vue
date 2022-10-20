<template>
  <div class="selectWrapper">
    <div class="selectItem day">Day:<span class="selectedData selectDay">today</span></div>
    <div class="selectItem time">Time:<span class="selectedData selectTime">after 1 hour</span></div>
    <div class="selectItem tag">Tag:<span class="selectedData selectTag">missing</span></div>
    <div class="selectItem category">Category:<span class="selectedData selectCategory">missing</span></div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.selectWrapper {
    margin: 0 auto;
    width: 86%;
    display: flex;
    justify-content: space-between;
    font-size: 16px;
    margin-top: 10px;
    color: gray;
}
.selectedData {
    color: white;
    font-size:15px;
    cursor: pointer;
    background:linear-gradient(#1c1e2b,#191b26,#191b26,#202230);
    padding-left: 4px;
    padding-right: 4px;
    padding-bottom: 2px;
    padding-top: 2px;
    border-radius: 6px;
    box-shadow: 1px 1px 5px rgb(14, 14, 14);
}
</style>