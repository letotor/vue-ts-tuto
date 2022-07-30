<template>
  <div class="app">
    <span v-for="job in jobs">
      
      {{job.title}} {{job.location}} {{job.salary}}
      <button @click="changeName('test')">Change</button>
    </span>

  </div>
</template>


<script  lang="ts">
import { defineComponent, ref, reactive, PropType, toRefs } from 'vue'
import Job from './types/Job'
import JobList from './components/JobsList.vue'

export default defineComponent({
  //  props :{
  //   msg: "message" as  PropType<umber>,
  // },
setup(props) {
 
  const state = reactive({
      name : 'totottt',
      age : 25 as string | number
  })

  //state.name = 25 /// cannot chantge type ici
  const test = ref('link') // automatique inference de type des lors de la ref // c'est une reference a un objet et non une value
  // as number | string  ce n'est pas possible
  const tests =ref<number | string>(25) /// ici avec generique on peut changer la reference . Ca ecrase le type de la reference interne
//lié aref
  let firstname = ref("toto")  


const jobs = ref<Job[]>([
  {title: "dev JS", location : "nantes",salary : 30000 , id:1},
  {title: "dev front", location : "nantes",salary : 28000 , id:2},
  {title: "dev full", location : "nantes",salary : 30000 , id:3},
  {title: "DAta engeneer", location : "nantes",salary : -100 , id:4},
])


const changeName = (name : string)=> {
  console.log('test', name)
  return firstname.value = 'modif'
}

  return  {
    ...toRefs(state),

    props,
    jobs,
    firstname ,
    changeName
  }


}


})
</script>



<style scoped>

</style>
