<template>
  <div>
    <h1>Create an Event, {{ user.name }}</h1>
    <p>This event was created by {{ user.id }}</p>
    <p>There are {{ catLength }} categories</p>
    <ul>
      <li v-for="cat in categories" :key="cat">{{ cat }}</li>
    </ul>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  /*computed: {
   
    userName() {
      return this.$store.state.user.name
    },
    userID() {
      return this.$store.state.user.id
    }
  }*/
  // computed: mapState({
  /*
    userName: state => state.user.name,
    userID: state => state.user.id,
    categories: state => state.categories
    */
  /*
    user: 'user',
    categories: 'categories'
    */
  // })
  computed: {
    catLength() {
      return this.$store.getters.catLength
    },
    ...mapState(['user', 'categories'])
  }
}
</script>

<style scoped></style>
