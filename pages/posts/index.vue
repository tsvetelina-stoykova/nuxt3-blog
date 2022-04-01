<template>
    <div class="flex flex-col h-screen ">
        <Header />
        <Content /> 
        
        <ul class=" m-auto justify-center">
            <li v-for="post of posts" :key="post.id" class="mb-8">
                <NuxtLink :to="`/posts/${post.id}`" class="flex flex-col items-center bg-white rounded-lg border shadow-md md:flex-row md:max-w-xl hover:bg-gray-100 dark:border-gray-700 dark:bg-gray-800 dark:hover:bg-gray-700">
                    <div class="flex flex-col justify-between p-4 leading-normal">
                    <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{{ post.title }}</h5>
                    
                    </div>
                </NuxtLink>
            </li>
        </ul>
       
        <Footer />
    </div>
</template>

<script setup>
    //set useState composable with key posts for shared state among pages
    const posts = useState('posts', () => null);
    const route = useRoute()


    // fetch JSON object from https://jsonplaceholder.typicode.com  API 
    const { data } = await useFetch('https://jsonplaceholder.typicode.com/posts/');
    posts.value = data;

    
    useMeta({
    title: 'Posts'
    })
 
</script>