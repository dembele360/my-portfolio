<script setup>
import { defineComponent, reactive } from 'vue';

defineComponent({
    name: 'Timelines',
});

const timelines = reactive([


    {
        id: 0,
        icon: 'mdi-briefcase-variant',
        color: 'blue-darken-3',
        title: 'Fabonic Ltd',
        position: 'Software Engineer',
        period: 'DEC 2021 — NOWADAYS',
        description: 'Working on various software development projects.'
    },
    {
        id: 1,
        icon: 'mdi-book-education',
        color: 'blue-darken-3',
        title: 'Mzumbe University (MU)',
        position: 'Bachelor of Science in Information and Communication Technology with Business',
        period: '2018 - 2021',
        description: 'Pursued a degree focused on ICT and business applications.'
    },
    {
        id: 2,
        icon: 'mdi-book-education',
        color: 'amber darken-1',
        title: 'Nainokanoka Secondary School',
        position: 'Advanced Certificate in Secondary Education',
        period: '2016 - 2018',
        description: 'Completed advanced secondary education.'
    },
    {
        id: 3,
        icon: 'mdi-book-education',
        color: 'cyan lighten-1',
        title: 'Lemara Secondary School',
        position: 'Certificate of Secondary Education (CSEE)',
        period: '2012 – 2015',
        description: 'Completed secondary education.'
    },
    {
        id: 4,
        icon: 'mdi-book-education',
        color: 'cyan lighten-1',
        title: 'Lemara Primary School',
        position: 'Certificate in Primary Education',
        period: '2005 – 2011',
        description: 'Completed primary education.'
    },

]);

</script>

<template>
    <div class="timeline mt-5">
        <h5 class="text-h5 text-uppercase text-center text-deep-purple-accent-1">Education & work</h5>
        <v-timeline class="mt-5">
            <v-timeline-item v-for="timeline in timelines" :key="timeline.id" :dot-color="timeline.color"
                :icon="timeline.icon" size="large">
                <template v-slot:opposite>
                    <div :class="`pt-1 headline font-weight-bold text-button text-${timeline.color}`"
                        v-text="timeline.period"></div>
                </template>
                <div>
                    <h2 :class="`mt-n1 headline font-weight-light mb-4 text-${timeline.color}`">
                        {{ timeline.title }}
                    </h2>
                    <h5 :class="`text-button text-${timeline.color}`">{{ timeline.position }}</h5>
                    <span class="text-subtitle-2">{{ timeline.description }}</span>
                </div>
            </v-timeline-item>
        </v-timeline>
    </div>
</template>
