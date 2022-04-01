<template>
    <div class="flex flex-col h-screen justify-between">
        <Header />
        <Content />
        <Footer />
    </div>
</template>


<script setup>

    const route = useRoute()
    
    useMeta({
    title: 'Demo'
    })
</script>