<template>
    <section id="experiences" class="part-container">
        <Header text="EXPERIENCES" icon="monitor.svg"/>
        <ExperienceBox v-for="(experience, index) in experiences" :key=index 
            :role=experience.role
            :company=experience.company
            :location=experience.location
            :period=experience.period
            :descriptions=temporary_text
            :is_final=is_final_in_list(index)
        />
    </section>
</template>
<script>
import Header from '../molecules/Header'
import ExperienceBox from '../molecules/ExperienceBox'

export default {
    name:'Experiences',
    components: {
        Header,
        ExperienceBox
    },
    data: () => ({
        temporary_text: `Lorem ipsum dolor sit amet, consectetur adipiscing elit. 
            Curabitur placerat turpis in diam ultrices, sed maximus neque vestibulum. 
            Suspendisse pulvinar augue a mi imperdiet egestas. 
            Phasellus in lacus porta, tincidunt est eu, rutrum purus. 
            Mauris sed tincidunt metus.Nam consectetur non sapien ac.`,
        experiences: [
            { role:"Web Developer",         company: "Septeni Technology",  location:"Hanoi",       period:"2019-2020" },
            { role:"IT Support",            company: "Emma & Tom",          location:"Melbourne",   period:"2019" },
            { role:"Teaching Assistant",    company: "Code Camp",           location:"Melbourne",   period:"2018" },
            { role:"Intern Web Developer",  company: "FPT Software",        location:"Hanoi",       period:"2017-2018" },
        ]
    }),
    methods: {
        is_final_in_list(index) {
            return index === this.experiences.length - 1 ? true : false
        }
    }
}
</script>
<style scoped>
</style>