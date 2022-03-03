<template>
<div>
    <AppHeader />
    <div class="row">
        <div class="col-lg-2">
        <SideBar />
        </div>
        <div class="col-lg-10">
        <Nuxt />
        </div>
    </div>
    <AppFooter />
</div>
</template>

<script>
import AppHeader from '../components/AppHeader.vue'
import AppFooter from '../components/AppFooter.vue'
import SideBar from '../components/SideBar.vue'
export default {
    components: {
        AppHeader,
        AppFooter, 
        SideBar
    }
}
</script>
<style scoped>

</style>