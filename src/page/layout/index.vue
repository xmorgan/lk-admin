<template>
<!-- styles/sidebar.scss -->
<div class="app-wrapper" :class="{hideSidebar:!sidebar.opened}">
    <sidebar class="sidebar-container"></sidebar>
    <div class="main-container">
        <navbar></navbar>
        <tags-view></tags-view>
        <app-main></app-main>
    </div>
</div>
</template>

<script>
import { Navbar, Sidebar, AppMain, TagsView } from './components'

/**
 * sidebar => store.app.sidebar
 */

export default {
    name: 'layout',
    components: {
        Navbar,
        Sidebar,
        AppMain,
        TagsView
    },
    computed: {
        sidebar() {
            console.log('layout component sidebar.opened =>', this.$store.state.app.sidebar.opened)
            return this.$store.state.app.sidebar
        }
    },
    mounted() {
        // console.log('layout component mounted =>', this.$store.state.app.sidebar)
    },
    updated() {
        // console.log('layout component updated =>', this.$store.state.app.sidebar)
    }
}
</script>

<style rel="stylesheet/scss" lang="scss" scoped>
@import "../../styles/mixin.scss";
.app-wrapper {
    @include clearfix;
    position: relative;
    height: 100%;
    width: 100%;
}
</style>
