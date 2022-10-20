<template>
    <div class="additionalItemWrapper">
        <div class="content" v-if="hidden">
            <div class="Title">Today's progress:</div>
            <div class="progressItemWrapper"
            v-for="(progress) in progresses"
            :key="progress.id"
            >
                <div class="templateProgressGoalItems progress">
                    <span class="taskPlaceholder"> task:</span>
                    <span class="task">{{progress.task}}</span>
                    <span> completed in:</span>
                    <span class="progressTime">{{progress.time}}</span>
                    
                </div>
            </div>
        </div>
        <div class="content" v-if="hidden">
            <div class="Title">Goals for 1 year:</div>
            <div class="goalItemWrapper"
            v-for="goalItem in goals"
            :key="goalItem.id"
            >
                <div class="templateProgressGoalItems goal">
                    {{goalItem.goal}}
                    <span class="goalData">{{goalItem.date}}</span></div>
            </div>
            <div></div>
        </div>
    </div>
</template>

<script>
export default {
data() {
    return {
    }
}
}
</script>

<style scoped>
.additionalItemWrapper {
    margin: 0 auto;
    width: 90%;
    margin-top: 10px;
}
.additionalItemWrapper .content {
width: 100%;
background-color: #2B2E38;
border-radius: 10px;
margin-bottom: 6px;
box-shadow: 1px 1px 5px rgb(14, 14, 14);
padding-bottom: 10px;
}
.additionalItemWrapper .Title {
    color: gray;
    font-size: 16px;
    padding: 17px;
    padding-top: 5px;
    padding-bottom: 5px;
    cursor: pointer;
}
.templateProgressGoalItems {
width: 100%;
margin: 0 auto;
background-color:#101118;
padding: 7px;
font-size: 16px;
border-radius: 10px;
padding-left: 14px;
}
.progress {
    font-size: 12px;
    color: rgba(128, 128, 128, 0.575);
}
.goal {
    color: gold;
}
.progressTime {
    color: white;
}
.goalData {
    color: deeppink;
}
.task {
    font-size: 16px;
    color: white;
}
.progressItemWrapper, .goalItemWrapper{
display: flex;
justify-content: space-between;
width: 95%;
margin: 0 auto;
margin-bottom: 7px;
}
</style>