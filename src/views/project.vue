<template>
  <div class="project page">
      <p>{{myProject[0].name}}</p>
    <!-- <div
    v-for= "project in dataProjects"
    :key="project.name">
      <h1>{{project.name}}</h1>
      <img class="projectImg" :src="project.src" alt="">

    </div> -->
  </div>
</template>


<!-- "../assets/img/linus-carlson-nightime-vip-3.jpg" -->


<script>
import dataProjects from '../constants/Projects'
export default {
  data() {
    return{
      dataProjects,
      myProject: null
    }
  },
  created(){
    this.myProject = dataProjects.filter(project => project.name === this.$route.params)
    console.log('myProject', this.myProject)
    console.log('projectId params', this.$route.params.projectId)
    console.log(dataProjects)
  }
}
</script>
