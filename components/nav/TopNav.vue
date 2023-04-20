<template>
    <div class="nav">
        <div class="item home">
            <span><NuxtLink class="router" to="/">Strona domowa</NuxtLink></span>
        </div>
        <div class="item about">
            <span><NuxtLink class="router" to="/onas">O nas</NuxtLink></span>
        </div>
    </div>
</template>
<script>

</script>

<style scoped>
.nav {
    display: flex;
    border-bottom: 5px solid #d6d6b1;
    background-color: #494331;
    height: 70px;
    width: 100%;
    min-height: 70px;
    max-width: 100vw;
    min-width: 200px;
    flex-wrap: wrap;
}

.item{
    font-size: 24px;
    align-self: center;
    text-decoration: none;
    margin-right: 20px;

}

.router{
    text-decoration: none;
    font-weight: 600;
    color: white;
}

.home{
    margin-left: 10px
}


</style>