<template>
    <div class="sidebar text-center pt-4">
        <nuxtLink to="/" class="m-5"> Home</nuxtLink>
        <ion-icon name="home"></ion-icon>
        <nuxtLink to="/debtors" class="m-5">Debtors</nuxtLink>
        <nuxtLink to="/Cleared" class="m-5">Cleared</nuxtLink>
        <nuxtLink to="/" class="m-5">Cleared</nuxtLink>


    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
.sidebar {
    height: 90vh;
    width: 100%;
    border-right: 1px solid black;
    background-color: rgb(18, 18, 133);
}

a {
    color: white;
    text-decoration: none

}
ion-icon {
  color: white;
}
</style>