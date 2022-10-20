<template>
<div class="themeSelectWrapper">
    <div class="themeTemplate darkThemeWrapper">
        <input type="radio" name="themeSelect" class="checkbox hidden">
        <label for="themeSelect" class="checkboxLabel"></label>
        Dark theme
    </div>
    <div class="themeTemplate lightThemeWrapper">
        <input type="radio" name="themeSelect" class="checkbox hidden">
        <label for="themeSelect" class="checkboxLabel"></label>
        Light theme
    </div>
    <div class="themeTemplate pinkThemeWrapper">
        <input type="radio" name="themeSelect" class="checkbox hidden">
        <label for="themeSelect" class="checkboxLabel"></label>

        Pink theme
    </div>
</div>
</template>

<script>
export default {

}
</script>

<style scoped>
.themeSelectWrapper {
    width: 280px;
    background-color: #2b2e38;
    border-radius: 15px;
    font-size: 16px;
    margin: 0 auto;
    margin-top: 15px;
    padding-top:15px;
    padding-bottom: 7px;
}
.themeTemplate {
    width: 80%;
    margin: 0 auto;
    border-radius: 10px;
    margin-bottom: 8px;
    padding: 7px 14px;
    display: flex;
    align-items: center;
    position: relative;
}
.checkbox {
    opacity: 0;
    width: 18px;
    height: 18px;
    position: absolute;
    margin-left: 1px;
}
.checkboxLabel {
    display: block;
    width: 13px;
    height: 13px;
    border-radius: 50%;
    border: 1px solid black;
    margin-right: 10px;
}
.checkbox:checked + .checkboxLabel {
    background-color: #ff14918a;
}
.lightThemeWrapper {
color: rgb(0, 0, 0);
background: linear-gradient(90deg, #191b26,#fff);
}
.pinkThemeWrapper {
color: rgb(255, 118, 141);
background: linear-gradient(90deg,#191b26,pink);
}
.darkThemeWrapper {
color: #ffffff;
background: linear-gradient(90deg, #191b26, black);
}
</style>