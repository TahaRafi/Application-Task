<template>
  <div id="main">
    <h1>Application Test</h1>
      <div v-for="(value,index) in listOfNumbers" v-bind:key="index">
      <input type="Number"  v-model="value.number"  @change="onChange()" min="1" max="10" ><br>
      </div>
      <button @click="addInput()">{{sum}}</button><br>
      </div>
</template>

<script>
export default {
  name: 'NumberInput',

  data(){
    return {
        listOfNumbers:  [
          {
            number: ''
          }
        ] ,
        sum: 0 ,
    }
  },
  
  methods : {

    addInput(){
      this.listOfNumbers.push({
        number: ''
      } 
      ); 
    },

     onChange() {
        this.sum=0;
        for (var i = 0; i < this.listOfNumbers.length; i++) {
        this.sum = this.sum + Number(this.listOfNumbers[i].number);
       }     
       }

  }
}
</script>


<style scoped>
#main {
  margin: 20px auto;
  max-width: 700px;
}
input {
  font-size: 30px;
  border: 1px double rgb(102, 97, 96) ;
  border-radius: 4px;
   text-align: center;
   width: 380px;
}
button {
 font-size: 30px;
  border: 1px double rgb(102, 97, 96) ;
  border-radius: 4px;
  width: 380px;
}
</style>
