<script setup lang="ts">
import { ref } from 'vue';
import { supabase } from '@/lib/supabaseClient';
import type { Tables } from 'database/types';

const projects = ref<Tables<'projects'>[] | null>();

(async () => {
    const { data, error } = await supabase.from('projects').select()

    if (error) console.log(error)

    projects.value = data;

    console.log({ projects: data })
})()
</script>
<template>
    <div>
        <h1>List of projects</h1>
        <ul>
            <li v-for="project in projects" :key="project.id">
                {{ project.name }}
            </li>
        </ul>
    </div>
</template>