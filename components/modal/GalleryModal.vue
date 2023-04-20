<template>
    <div class="modal">
        <div class="gallery">
            <button type="button" @click="close"> X </button>
            <SmallImages class="gallery-modal"/>
        </div>
    </div>
</template>
<script>
import SmallImages from '../gallery/smallImages.vue';

export default {
    name: "GalleryModal",
    methods: {
        close() {
            this.$emit("close");
        },
    },
    components: { SmallImages }
};
</script>

<style scoped>
.modal {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    scale: 1;
    z-index: 2;
}

.gallery{
    width: 500px;
    height: 350px;
    background-color: white;
    border: 2px solid black;
    scale:2;
    flex-direction: column;
}

.gallery-modal{
    display: grid;
    grid-auto-flow: column;
}
</style>