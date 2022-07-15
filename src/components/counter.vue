<template>
  <div class=" ">
    <h1 >Vue Counter</h1>
    <h1 class=" counter">{{counter}}</h1>
    <button @click="subtractFromCounter(parseInt(value))">-</button>
    <input type="number" v-model="value" />
    <button @click="addToCounter(parseInt(value))">+</button>
    <div>
    <button class="btn" @click="addRandomNumber">addRandomNumber</button>
    </div>
  </div>
</template>

<script>
import { mapState, mapMutations, mapActions } from 'vuex'
export default {

  data(){
    return{
      value: 0
    }
  },
  computed:{
    ...mapState(["counter"])
  },
  methods:{
    ...mapMutations(["addToCounter", "subtractFromCounter"]),
    ...mapActions(["addRandomNumber"])
  }
}
</script>
 
<style scoped>
.counter{
  font-size: 5rem;
}
button{
  background-color: teal;
  color: white;
  border-radius: 100%;
  border: none;
  width: 2rem;
  height: 2rem;
  font-weight: 900;
  cursor: pointer;
}
input{
  padding: 0.4rem;
  margin: 0.0.5rem;
  text-align: center;
}
.btn{
  width:auto;
  margin: 10px;
  cursor: pointer;
  border-radius: 0.5rem;
}
 
</style>