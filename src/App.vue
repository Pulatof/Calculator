<template >
  <h2>Calculator</h2>
  <div id="app">
    <div class="main">
    <input class="input" type="text" v-model="result" placeholder="0">
    <button @click="input(number)" class="calc number" v-for="number in numbers">{{ number }}</button>
    <button @click="input(operation)" class="calc oper" v-for="operation in operations">{{ operation }}</button>
    <button @click="reset()" class="calc oper" >C</button>
    <button @click="calc()" class="calc oper" >=</button>
  </div>
  </div>
</template>
<script>
export default {
  data(){
      return{
        result:'',
        numbers:[1,2,3,4,5,6,7,8,9,0],
        operations:['+','-','*','/',],
      }
    
  },
  methods:{
    input: function(obj){
      this.result+=obj
    },
    reset:function(){
      this.result = ''
    },
    calc:function(){
      this.result = eval(this.result)
    }

  }
}
</script>
<style scoped>


*{
  font-family: serif;
  transition: 0.3s all;
  font-weight: 600;
}


#app{
  width: 200px;
  box-shadow: 0 3px 15px gray;
}
.input{
width: 200px;
font-size: 18px;
border: none;
color: black;
padding:10px 0px 10px 0px;
text-align: right;

}

.main{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  width: 100%;
}

.calc{
  flex: 33%;
  height: 50px;
  font-size: 18px;
  border: none;
}
  
</style>