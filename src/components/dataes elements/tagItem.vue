<template>
  <div class="tagItemWrapper">
    <div class="addNewTag"> New Tag </div>
    <div class="tagsSelectWrapper">
      <div class="tagItem selectTag">TagExample 1</div>
      <div class="tagItem">TagExample 1</div>
      <div class="tagItem">TagExample 1</div>
      <div class="tagItem">TagExample 1</div>
      <div class="tagItem">TagE</div>
      <div class="tagItem">TagExample 1</div>
      <div class="tagItem">TagExample 1</div>
      <div class="tagItem">TagExample 1</div>
      <div class="tagItem">TagExample 1</div>
      <div class="tagItem">TagExample 1</div>
      <div class="tagItem">TagExample 1</div>
      <div class="tagItem">TagExample 1</div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
::-webkit-scrollbar {
  width: 7px;
}

/* Track */
::-webkit-scrollbar-track {
  box-shadow: inset 0 0 5px grey;
  border-radius: 5px;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: rgba(161, 161, 153, 0.336);
  border-radius: 10px;
}
.tagItemWrapper {
  width: 133px;
  height: 217px;
  background: radial-gradient(rgb(56, 52, 27),black);
  border: 1px solid rgba(0, 0, 0, 0.363);
  overflow-y: scroll;
  border-radius: 10px;
}
.addNewTag {
    display: block;
    color: white;
    font-size: 15px;
    cursor: pointer;
    background: linear-gradient(#1c1e2b, #191b26, #191b26, #202230);
    padding-left: 4px;
    padding-right: 4px;
    padding-bottom: 2px;
    padding-top: 2px;
    border-radius: 6px;
    box-shadow: 1px 1px 5px rgb(14, 14, 14);
    width: fit-content;
    max-width: 90px;
    min-width: 53px;
    overflow: hidden;
    text-align: center;
    margin: 0 auto;
    margin-top: 5px;
    margin-bottom: 5px;
}
.tagsSelectWrapper {
  display: flex;
  flex-direction: column;
}
.tagItem {
max-width:100%;
height: 25px;
margin: 0 3px;
overflow: hidden;
color: rgb(168, 168, 168);
}
.selectTag {
background-color: #ff14918e;
border-radius: 6px;
padding: 0 4px;
box-sizing: border-box;
}
</style>