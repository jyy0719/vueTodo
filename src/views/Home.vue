<template>
  <div class="home">
    <h1>TODO LIST</h1>
    <p>할 일은 해야하지 않겠니?</p>
    <!-- <input type="text" value="오늘 할 일" v-model="newPlayer" v-on:keyup.enter="addPlayer" > -->
      <!--  v-on:keyup.enter  @keyup.enter  대체 가능 -->
    <!-- <input @keyup="whatodo" :value="text" type="text" id="inputText">     v-on:keyup.enter="addList"-->
    <input type="text" v-model="newPlan" >
    <button v-on:click="addList" class="test_btn1">Click me </button>
    <hr>
    {{newPlan}}<br>
    <ul>
      <li v-for="(list,index) in lists" v-bind:key="index">
          [ {{index+1}} ] - {{list.name}}   <button v-on:click="deleteList(index)" class="test_btn1">끝 ^_^</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data: function(){
    return{
      text : '',
      lists : [
        {name : '빨래'}
      ],
      newPlan : '',
      index : '',
    }
  },
  methods:{
    addList(event){
      event.preventDefault()
     // alert("이건 에러 안나냐")
      this.lists.push({name: this.newPlan})
      this.newPlan='' 
    },
    deleteList(index){
     // event.preventDefault()
      alert("끝이다")
      this.lists.pop(index)
      
    }
  }
}
</script>
<style scoped>
  h1{
    color: #42b983;
  }
  ul{
    list-style: none;
  }
  .test_btn1{ margin-right:-4px; } #test_btn2{ margin-left:-3px; }

</style>
