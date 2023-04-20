<template>
  <div>
    <TopNav />
    <h1>Strona domowa</h1>
    <smallImages @visible="showModalVisible()"/>
    <GalleryModal v-show="isModalVisible" @close="closeModal()"/>
  </div>
</template>

<script>
import TopNav from '../components/nav/TopNav.vue'
import smallImages from '../components/gallery/smallImages.vue';
import GalleryModal from '../components/modal/GalleryModal.vue';
export default {
  name: 'IndexPage',
  components: { TopNav, smallImages, GalleryModal },
  data(){
    return {
      isModalVisible: false,
    };
  },
  methods: {
    showModalVisible() {
      console.log("wchodzi")
      this.isModalVisible = true
    },
    closeModal(){
      this.isModalVisible = false
    }
  }
}
</script>