<template>
  <div class="container">
    <h2>Project search</h2>
    <input type="text" @input="searchProject = $event.target.value">
    <p>Total projects: {{projects.length}}, matches:{{getFilteredProjects.length}}</p>
    <ul class="list">
      <li v-for="(project,index) in getFilteredProjects()" :key="index" class="item">
        {{project}}
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HwSearchProject',
  data () {
    return {
      searchProject: '',
      projects: ['WebStudio', 'Filmoteka', 'KidsLike']
    }
  },
  methods: {
    getFilteredProjects () {
      return this.projects.filter(project => project.toLocaleLowerCase().includes(this.searchProject.toLowerCase()))
    }
  }
}
</script>
