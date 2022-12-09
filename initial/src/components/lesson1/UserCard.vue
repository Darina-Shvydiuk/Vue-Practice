<template>
  <div class="user-card">
    <h1>Junior Frontend Developer</h1>
    <p class="user-name"> {{getFullName}}</p>
    <ul class="user-list">
      {{listTechSkills}}
      <li class="user-item">
        {{js}}
      </li>
      <li class="user-item">
        {{react}}
      </li>
      <li class="user-item">
        {{vue}}
      </li>
    </ul>
    <h2>Pet Projects:</h2>
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
      vue: 'Vue'
    }
  },
  computed: {
    getFullName () {
      return `${this.firstName}  ${this.lastName}`.toUpperCase()
    }
  }
}
</script>
<style >
.user-card{
  display: block;
}
.user-name{
text-align: center;
font-size: 20px;
}
.user-list{
  display: flex;
  justify-content: center;
  flex-direction: column;
  list-style: none;
  margin-left: 0 auto;
  margin-right: 0 auto;
  padding: 0;
}
</style>
