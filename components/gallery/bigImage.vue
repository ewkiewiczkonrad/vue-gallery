<template>
    <div>
        <img @click="openModal()" :src="image" class="img">
    </div>
</template>
<script>

export default {
  name: 'BigImage',
  props: {
    image:{
        type: String,
        default: () => 'pusty'
    }
  },
  methods:{
        openModal(){
            console.log("big")
            this.$emit("open")
        }
      }
}
</script>

<style scoped>
.img{
    width: 200px;
    height: 200px;
}

</style>
