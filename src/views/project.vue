<template>
  <div class="project page">
      <p>{{myProject[0].name}}</p>
      <img class="projectImg" :src="myProject[0].src" alt="">
  </div>
</template>


<script>
import dataProjects from '../constants/Projects'
export default {
  data() {
    return{
      dataProjects,
      myProject: null,
      Mehdi: null
    }
  },
  created(){
    this.myProject = dataProjects.filter(project => project.name === this.$route.params.projectId)
    // console.log('myProject', this.myProject)
    // console.log('projectId params', this.$route.params.projectId)
    // console.log(dataProjects)
  },

  watch: {
  '$route':  function  (to, from){
    this.myProject = dataProjects.filter(project => project.name === this.$route.params.projectId)
      // console.log('fired', this.projectId)
      // console.log('to', to)
      // console.log('from', from)
    }
  }

}
</script>
