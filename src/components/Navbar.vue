<template>
  <div class="">
    <nav class="navs">
      <router-link class="spacing" v-for="routes in links" 
      v-bind:key="routes.id"
      :to="`${routes.page}`">{{routes.text}}</router-link>
    </nav>
  </div>
</template>

<script>
export default {
    data() {
    return {
      links: [
        {
          id: 0,
          text: 'Home',
          page:'/'
        },
        {
          id: 1,
          text: 'About',
          page:'/About'
        },
      ]
    }
  }
}
</script>

<style scoped>

*, ::after, ::before {
    box-sizing: border-box;
}

nav{
  background-color: #f6eee5;
  padding: 30px
}
.spacing {
  margin-right: 10px;
}

.navs {
  height: 90px;
}

.nav a {
  padding: 20px
}
</style>