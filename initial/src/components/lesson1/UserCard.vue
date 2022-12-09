<template>
  <div class="card">
    <h1>Junior Frontend Developer</h1>
    <p class="name"> {{getFullName}}</p>
    <ul class="list">
      {{listTechSkills}}
      <li class="item">
        {{js}}
      </li>
      <li class="item">
        {{react}}
      </li>
      <li class="item">
        {{vue}}
      </li>
    </ul>
    <h2>Pet Projects: {{projects.length}}</h2>
    <ul class="list">
      <li v-for="(project, index) in projects" :key="index" class="item">
      {{`${index + 1} ${getProjectsList(project)}`}}
      </li>
    </ul>
    <button type="button" @click="currentPage--" class="btn">
      Previous
    </button>
    <button v-for="(page) in pages" :key="page" type="button" @click="currentPage = page" class="btn">
    {{page}}
    </button>
    <button type="button" @click="currentPage++" class="btn">
      Next
    </button>
    <p>
      Page {{currentPage}} from {{pages}}
    </p>
  </div>
</template>
<script>
export default {
  name: 'UserCard',
  data () {
    return {
      firstName: 'Darina',
      lastName: 'Shvydiuk',
      listTechSkills: 'Tech skills:',
      js: 'JS',
      react: 'React',
      vue: 'Vue',
      projects: [
        {
          title: 'Filmoteka',
          language: 'JS'
        },
        {
          title: 'KidsLike',
          language: 'React'
        },
        {
          title: 'WebStudio',
          language: 'HTML5'
        }
      ],
      pages: 3,
      currentPage: 1
    }
  },
  computed: {
    getFullName () {
      return `${this.firstName}  ${this.lastName}`.toUpperCase()
    }
  },
  methods: {
    getProjectsList (project) {
      return `${project.title}  ${project.language}`
    },
    loadProjects (page) {
      console.log(`Loading projects: page ${page}`)
    }
  },
  watch: {
    currentPage (page) {
      this.loadProjects(page)
    }
  }
}
</script>
<style >
.card{
  display: block;
}
.name{
text-align: center;
font-size: 20px;
}
.list{
  display: flex;
  justify-content: center;
  flex-direction: column;
  list-style: none;
  margin-left: 0 auto;
  margin-right: 0 auto;
  padding: 0;
}
.item{
  margin-bottom: 5px;
}
.btn{
  border-radius: 8px;
  padding: 5px;
margin-right: 3px;
}
</style>
