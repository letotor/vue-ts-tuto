<template>
    <div>
    <ul  >
        <li v-for="job in jobs" :key="job.id"></li>
        <h2>{{job.title}}</h2>
    </ul>
    </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
// import Job from '@/types/Job'


export default defineComponent({
     props:{
            jobs:{
                required:true,
                type: Array as PropType<Job[]>
            }
        },
    setup (props([
          {title: "dev JS", location : "nantes",salary : 30000 , id:1},
  {title: "dev front", location : "nantes",salary : 28000 , id:2},
  {title: "dev full", location : "nantes",salary : 30000 , id:3},
  {title: "DAta engeneer", location : "nantes",salary : -100 , id:4},
    ]){
  return {props}
    } 
    )}

       

      
    

</script>

<style scoped>

</style>