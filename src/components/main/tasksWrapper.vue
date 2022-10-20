<template>
  <div class="tasksWrapper">

    <div class="buttonsTitle"></div>

    <div class="todoItem">    
      <div class="checkboxTaskWrapper">
        <div class="completedCheckbox">
        </div>
      </div>
      <div class="removeButtonWrapper">
        <div class="removeButton">&times;</div>
    </div>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style scoped>
/* width */
::-webkit-scrollbar {
  width: 7px;
}

/* Track */
::-webkit-scrollbar-track {
  box-shadow: inset 0 0 5px grey;
  border-radius: 10px;
  margin-left: 10px;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: rgba(128, 128, 128, 0.836);
  border-radius: 10px;
}
.tasksWrapper {
    width: 90%;
    margin: 0 auto;
    background-color: #2b2e38;
    overflow-y: auto;
    height: 50vh;
    border-radius: 20px;
    padding-top: 10px;
    box-shadow: 1px 1px 5px rgb(14 14 14);
    margin-top: 10px;
}
.todoItem {
  display: flex;
  align-items: center;
  background-color: #3c404b;
  width: 93%;
  margin: 0 auto;
  padding: 7px;
  font-size: 16px;
  border-radius: 10px;
  padding-left: 14px;
  margin-bottom: 7px;
  background: linear-gradient(#1c1e2b, #191b26, #191b26, #202230);
}
.completedCheckbox {
  width: 13px;
  height: 13px;
  border-radius: 50%;
  border: 1px solid black;
  margin-right: 10px;
}
.deeppinkColor {
  background-color: #ff14919f;
}
.lineThrough {
  text-decoration: line-through;
  text-decoration-color: black;
  text-decoration-thickness: 2px;
}
.removeButtonWrapper {
  width: 10%;
  display: flex;
  justify-content: end;
  margin-right: 5px;
}
.removeButton {
  width: fit-content;
  font-size: 18px;
  color: gray;
  cursor: pointer;

}
.checkboxTaskWrapper {
  display: flex;
  align-items: center;
  width: 90%;
}
.buttonsTitle {
  color: gray;
  margin-left: 30px;
  margin-bottom: 10px;
  margin-top: -2px;
}
</style>