<template>
     <AboutComponent />
     <ProgressComponent />
     <StaffComponent />
     <SolutionsComponent />
     <WorkComponent />
     <ClientsComponent />
     <BlogComponent />
     <MapComponent />
     <ContactComponent />

</template>


<script>

import AboutComponent from './MainSections/AboutComponent.vue'
import ProgressComponent from './MainSections/ProgressComponent.vue'
import StaffComponent from './MainSections/StaffComponent.vue'
import SolutionsComponent from './MainSections/SolutionsComponent.vue'
import WorkComponent from './MainSections/WorkComponent.vue'
import ClientsComponent from './MainSections/ClientsComponent.vue'
import BlogComponent from './MainSections/BlogComponent.vue'
import MapComponent from './MainSections/MapComponent.vue'
import ContactComponent from './MainSections/ContactComponent.vue'





export default{
    name: "MainComponent",

    components: {
        AboutComponent,
        ProgressComponent,
        StaffComponent,
        SolutionsComponent,
        WorkComponent,
        ClientsComponent,
        BlogComponent,
        MapComponent,
        ContactComponent        
    }

}

</script>


<style scoped>
</style>