<template>
<NavBar />
<DashboardView />
<ServiceComponent/>
<ContactUs/>
</template>
<script>
import {
    defineComponent
} from 'vue';

// Components
import NavBar from '../components/NavBar.vue';
import DashboardView from '../components/DashboardView.vue';
import ServiceComponent from '../components/ServiceComponent.vue';
import ContactUs from '../components/ContactUs.vue';
export default defineComponent({
    name: 'HomeView',
    components: {
        NavBar,
        DashboardView,
        ServiceComponent,
        ContactUs,
    },
});
</script>
