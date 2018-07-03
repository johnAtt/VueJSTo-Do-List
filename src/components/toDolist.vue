
<template>

<div class="Main">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div class="holder">
        <form @submit.prevent="addTask">
            <input type="text" name="new-task" placeholder="I want to ..." v-model="newTask"/>
            {{ newTask }}
        </form>
        <p>Things to Do</p>
            <transition-group name="task-effect" tag="ul">
                <li v-for="(data, index) in doList" :key='index'><i class="fa fa-star" v-on:click="addFavorite(event)"></i>{{data.task}}
                    <button class="trash" v-on:click="doList.splice(index, 1)"><i class="trash fa fa-trash-o"></i></button> 
                    <button v-on:click="doneTask(data, index)"><i class="check fa fa-check"></i></button>
                    </li>
            </transition-group>
            <p>Things Done</p>
            <transition-group name="task-effect" tag="ul">
                <li v-for="(data, index) in doneList" :key='index'>{{data.Donetask}}
                    <button class="trash" v-on:click="doneList.splice(index,1)"><i class="trash fa fa-trash-o"></i></button>
                    <button v-on:click="returnTask(data, index)"><i class="check fa fa-arrow-circle-up"></i></button> 
                    </li>
            </transition-group>
    </div>
</div>

</template>

<script>
export default {
  name: "toDolist",
  data() {
    return {
      doList: [],
      doneList:[],
      newTask: "",
    };
  },
  methods: {
    addTask() {
      this.doList.push({ task: this.newTask });
      this.newTask = "";
    },
    doneTask(data, index){
       this.doneList.push({ Donetask: data.task });
       this.doList.splice(index,1);
    },
    returnTask(data, index){
        this.doList.push({ task: data.Donetask });
       this.doneList.splice(index,1);
    },
    addFavorite(event){
     
    }

  }
};
</script>

<style src="./toDolist.css">

</style>

