<template>
    <div class="card">
        <form @submit.prevent="addTask">
        <input type="text" v-model="task" class="addTaskInput">
          <button class="btn" type="submit">Add Task</button>
        </form>
    </div>
</template>

<script>

export default {
    name: "AddTask",
    data(){
        return{
            task : ""
        }
    },
    methods:{
        addTask(){
            if(this.task === "" || this.task.length <3){
                alert("Can't add empty field or less than 3 characters")
                return
            }
            this.$emit("add-task", this.task)
            this.task = ""
        }
    }
}
</script>

<style scoped>
.addTaskInput{
    padding: 5px 11px;
    font-size: 24px;
    font-family: inherit;
    border-radius: 38px;
    outline: none;
    border: 2px dashed cornflowerblue;
    margin: 14px 14px;
    background: #F3F2F6;
    max-width: 50%;
}
.addTaskInput:hover , .addTaskInput:focus{
    background: white;
}
.btn {
  padding: 9px 25px;
  border-radius: 100px;
  border: none;
  font-size: 21px;
  font-weight: bold;
  font-family: inherit;
  margin: 3px;
}
.btn:hover {
  background-color: #c9c9c9 !important;
  cursor: pointer;
}
</style>