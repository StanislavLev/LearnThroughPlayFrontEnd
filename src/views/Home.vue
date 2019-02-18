<template>
  <div>
    <div>
      <v-flex xs12 sm4>
        <v-select
          :items="addendsNum"
          label="Number of addends"
          v-model="addendsNumSelected" 
        ></v-select>
      </v-flex>
      Minimum number
      <input v-model="minNum">
      Maximum number
      <input v-model="maxNum">
      <v-flex xs12 sm4>
        <v-select
          :items="operations"
          label="Operations Allowed"
          v-model="operationsSelected" 
        ></v-select>
      </v-flex>
      <button on-click="showExercise()" >Generate!</button>
    </div> 
    <span v-for="i in addendsNumSelected" v-bind:key="i">
      <span>{{getRandomInt(minNum, maxNum)}}</span>
      <span>{{operationsSelected}}</span>
    </span>
  </div>
</template>

<script>

  export default {
    data(){
      return{
        addendsNum: [1,2,3,4,5],
        addendsNumSelected: "",
        minNum: 0,
        maxNum: 100,
        operations: ["+", "-", "*", "/"],
        operationsSelected: "",
      }
    },
    methods: {
      getRandomInt: function(min, max) {
        return Math.floor(Math.random() * (max - min + 1)) + min;
      }
    }

  }
</script>
