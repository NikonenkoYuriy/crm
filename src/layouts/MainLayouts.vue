<template>
    <div class="app-main-layout">
        <nav-bar @click="isOpen = !isOpen"></nav-bar>
        <side-bar v-model="isOpen"></side-bar>
        <main class="app-content" :class="{full:!isOpen}">
            <div class="app-page">
                <router-view />
            </div>
        </main>

        <div class="fixed-action-btn">
            <router-link class="btn-floating btn-large blue" to="/record">
                <i class="large material-icons">add</i>
            </router-link>
        </div>
    </div>

</template>

<script>
    import NavBar from '../components/app/NavBar.vue'
    import SideBar from '../components/app/SideBar.vue'
    export default {
        data: () => ({
            isOpen: true
        }),
        components: {
            NavBar: NavBar,
            SideBar: SideBar

        }
    }
</script>