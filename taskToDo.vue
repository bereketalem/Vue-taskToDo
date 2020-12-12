<template>

  <div class="hello">

     <div class="task">
     
         <div id="title">
           {{name}}
         </div> 
         
        <form @submit.prevent="addTask">
        
           <input type="text" placeholder="Enter a task to do.." v-model="taskName">
             <!-- {{ taskName }} just to check if what you write is typing... -->
             
        </form>

            <ul>
               <li v-for="(data,index) in Tasklist" 
                   v-bind:key="index">
                  <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24"><path d="M0 0h24v24H0V0zm0 0h24v24H0V0z" fill="none"/><path d="M16.59 7.58L10 14.17l-3.59-3.58L5 12l5 5 8-8zM12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8z"/></svg>{{data.taskName}}
                 <v-btn v-on:click="remove">x</v-btn>
              </li>
           </ul>
              <p>These are list of task to do</p>
      </div>
     
   </div>
  
</template>

<script>
export default {
  name: 'TaskToDo',
  data() {
   return {
     name: 'TEFLON',
     taskName: '',
     Tasklist: [
       {"taskName": "Bananer"},
       {"taskName": "Kaffe"},
       {"taskName": "Keso"},
       {"taskName": "Rolig keps med djurmotiv"}
     ]
     
   }
  },
  methods: {
    addTask () {
      this.Tasklist.push({taskName: this.taskName})
      this.taskName = '';
    },
    remove(id){
      this.Tasklist.splice(id,1);
  }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css";
@import "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.1/css/brands.min.css";



#title {
  text-align: center;
  margin-bottom: 1.7rem;
  font-size: 1.5rem;
  

}
v-btn{
  float:right;
  color:red;
}
ul, li, svg {
  padding-right: 1em;
}

.task {
  background: #fff;
}
ul {
  margin: 0;
  padding: 0;
  list-style-type: none;
}
ul li {
  padding: 20px;
  font-size: 1.3em;
  background-color: #E0EDf4;
  border-left: 5px solid #3EB3F6;
  margin-bottom: 2px;
  color: #3E5252;
  cursor: pointer;
}
p {
  text-align: center;
  padding: 30px 0;
  color: gray;
}
.container {
  box-shadow: 0px 0px 40px lightgray;
}

input {
  width: calc(100% - 40px);
  border: 0;
  padding: 20px;
  font-size: 1.3em;
  background-color: #323333;
  color: #687F7F;
}


</style>
