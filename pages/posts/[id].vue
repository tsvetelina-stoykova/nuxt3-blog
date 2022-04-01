<template>
    <div class="flex flex-col h-screen justify-between">
        <Header />
        <Content /> 
        <div class="mx-auto">
            <NuxtLink to="/posts" class="text-blue-400 text-sm">Back to all posts</NuxtLink>
            <div class="flex flex-col items-center bg-white rounded-lg border shadow-md md:flex-row md:max-w-xl">
                <div class="flex flex-col justify-between p-4 leading-normal">
                    <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{{ post.title }}</h5>
                    <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">{{ post.body }}</p>
                </div>
            </div>
            <!-- <h1 class="font-bold text-xl mt-4">{{ post.title }}</h1>
            <p class="font-bold text-xl mt-4">{{ post.body }}</p> -->
        </div>
        <Footer />
    </div>
</template>


<script setup>
import { useRoute } from 'vue-router';

const {params} = useRoute();
const post = useState('post', () => null);

 const { data } = await useFetch(`https://jsonplaceholder.typicode.com/posts/${params.id}`);
    post.value = data;

</script>