<template>
    <div>
        <div class="big-image-container">
            <button class="button button-left" @click="getPreviousImg()">&lt;</button>
        <bigImage @open="showModal()" class="bigImg" :image="bigImage.src" />
        <button class="button button-right" @click="getNextImg()">&gt;</button></div>
        <div class="small-images-container">
            <img v-for="image in images" :key="image.id" :src="image.src" class="img" @click="getBigImage(image)">
        </div>
    </div>
</template>
<script>
import bigImage from './bigImage.vue';
export default {

    name: 'SmallImage',
    data() {
        return {
            images: [
                {
                    id: 0,
                    src: "https://zpkwm.pl/wp-content/uploads/pustynia-37-800x533.jpg"
                },
                {
                    id: 1,
                    src: "https://www.medianauka.pl/geografia/grafika/krajobraz-nadmorski.jpg"
                },
                {
                    id: 2,
                    src: "https://m.wmwm.pl/2017/08/n/20-09-2017-fot-mieczyslaw-wieliczko-5783.jpg"
                },
                {
                    id: 3,
                    src: "https://www.pzstudio.pl/public/foto/photo/big/4703.jpg"
                }
            ],
            bigImage: {
                    id: 0,
                    src: "https://zpkwm.pl/wp-content/uploads/pustynia-37-800x533.jpg"
                }
        }
    },
    methods: {
        getBigImage(image) {
            this.bigImage = image
        },
        getPreviousImg(){
            if(this.bigImage.id === 0){
                this.bigImage = this.images[this.images.length-1]
            } else {
                this.bigImage = this.images[this.bigImage.id-1]
            } 
        },
        getNextImg(){
            if(this.bigImage.id === this.images.length-1){
                this.bigImage = this.images[0]
            } else {
                this.bigImage = this.images[this.bigImage.id+1]
            }
        },
        showModal() {
            this.$emit("visible")
    },
    },
    components: { bigImage }

}

</script>

<style scoped>
.img {
    width: 50px;
    height: 50px;
    margin-right: 10px;
}

.bigImg {
    margin-bottom: 10px;
}
.small-images-container{
    display: flex;
    justify-content: center;

}
.big-image-container{
    display: flex;
    justify-content: center;
}
.button{
    height: 25px;
    align-self: center;
}
.button-left{
    margin-right: -12px;
    z-index: 1;
}
.button-right{
    margin-left: -12px;
    z-index: 1;
}
</style>
