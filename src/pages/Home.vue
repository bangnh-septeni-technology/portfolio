<template>
    <div>
        <input class="checkbox" type="checkbox" id="check">
        <div class="background"></div>
        <portfolio-side-bar :active_tab=active_tab />
        <portfolio-content />
    </div>
</template>

<script>
import { bus } from '../main'
import PortfolioSideBar from '../components/templates/PortfolioSideBar'
import PortfolioContent from '../components/templates/PortfolioContent'

export default {
    name: 'Home',
    components: {
        PortfolioSideBar,
        PortfolioContent
    },
    data () {
        return {
            active_tab: "about"
        }
    },
    methods: {
        change_active_tab(tab) {
            this.active_tab = tab     
        },
    },
    created() {
        bus.$on('change_tab',(tab) => this.change_active_tab(tab))
    }
}
</script>
<style scoped>
.background {
    min-height: 100vh;
    height: 100%;
    width: 100%;
    z-index: -1000;
    position: fixed;
    left:0;
    top:0;
    background-color: var(--primary-bg-color);
}

.checkbox {
    display: none;
}
</style>