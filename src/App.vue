<template>
  <div id="app">
      <component :is="layout">
        <router-view/>    
      </component>
  </div>
</template>
<script>
    import emptyLayout from '@/layouts/EmptyLayouts.vue'
    import mainLayout from '@/layouts/MainLayouts.vue'

    export default {
        computed: {
            layout() {
                return (this.$route.meta.layout || 'empty') +  '-layout'
            }
        },
        components: {
            'empty-layout':emptyLayout, 
            'main-layout':mainLayout
        }
    }
</script>

<style lang="scss">
    @import '~materialize-css/dist/css/materialize.min.css';
    @import 'assets/index.css';
</style>
