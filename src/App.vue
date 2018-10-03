<template>
  <div id="app">
    <div class="nav">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
      <router-link v-for= "project in dataProjects" :key= "project.name" :to="{ name: 'project', params: { projectId: project.url }}">
        {{project.name}}
      </router-link>
    </div>

    <transition name="router-anim" enter-active-class="animated fadeInDown" leave-active-class="animated fadeOutDown">
      <router-view :key="$route.params.projectId"></router-view>
    </transition>

  </div>
</template>

<script>
import project from './views/project.vue'
import dataProjects from './constants/Projects'
export default {
  data () {
    return {
      dataProjects
    }
  },
  components: {
    project
  },
//   watch: {
//   '$route':  function  (to, from){
//
//   }
// }
  // mounted (){
  //   console.log(this.dataProjects)
  // }

}
</script>



<style src="./css/App.css"></style>
