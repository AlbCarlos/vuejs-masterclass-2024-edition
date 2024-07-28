<template>
    <div>
        <h1>Projects View</h1>
        <RouterLink :to="{ name: '/projects/[id]', params: { id: 1 } }">Go to porject 1</RouterLink>
    </div>
</template>