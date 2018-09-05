<template>
  <div class="project page">
    <div>Projects :
      <ul
      v-for= "item in projects"
      v-bind:key="item.id">
        <li>{{item.title}}</li>
      </ul>
    </div>
    <!-- <img class="" src= alt=""> -->
  </div>
</template>


<!-- "../assets/img/linus-carlson-nightime-vip-3.jpg" -->


<script>
export default {
  data() {
    return {
      projects: [
        { id: 0, title: 'Project 1'},
        { id: 1, title: 'Project 2'},
      ]
    }

  }
}
</script>
