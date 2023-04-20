<template>
    
    <div>
        <TopNav/>
        <h1>O nas</h1>
        <h2> strona </h2>
        <button @click="showInfo">Kliknij mnie</button>
    </div>
</template>
<script>
import TopNav from '../components/nav/TopNav.vue'
export default {
  name: 'OnasPage',
  components: {TopNav},

  methods: {
    showInfo: () => {
        console.log("Witaj w konsoli")
        alert("Witaj")
    }
  }
}
</script>

<style scoped>

</style>