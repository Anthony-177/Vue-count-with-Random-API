<template>
  <div class="History">
    <h4>HISTORY</h4>
    <div class="flex">
      <p v-for="(number, index) in history" :key="index" 
      :class="activeIndexes(parseInt(value)).includes(index) && 'bold'">
          {{number}}
      </p>
    </div>
        <input 
            placeholder="Search by Index" 
            type="number" 
            v-model="value"
        />
  </div>
</template>

<script>
import { mapState, mapGetters} from 'vuex'
export default {
    data() {
        return {
            value: 0
            }
        },
    computed: {
    ...mapState(["history"]),
     ...mapGetters(["activeIndexes"])
    }
 
}
</script>
 
<style scoped>
.History{
    color: red;
    margin-top: 7rem;
}
.flex{
    margin: 0 auto;
    width: 25rem;
    text-align: center;
    justify-content: center;
    display: flex;
    flex-wrap: wrap;
}
.flex p {
    margin: 1rem
}
.bold {
font-weight: 900;
color: green;
}
</style>