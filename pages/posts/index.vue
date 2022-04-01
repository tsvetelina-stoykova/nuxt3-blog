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

    const posts = useState('posts', () => null);


    const { data } = await useFetch('https://jsonplaceholder.typicode.com/posts/');
    posts.value = data;
 
</script>

// <a href="#" class="flex flex-col items-center bg-white rounded-lg border shadow-md md:flex-row md:max-w-xl hover:bg-gray-100 dark:border-gray-700 dark:bg-gray-800 dark:hover:bg-gray-700">
//   
//     <div class="flex flex-col justify-between p-4 leading-normal">
//         <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Noteworthy technology acquisitions 2021</h5>
//         <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological order.</p>
//     </div>
// </a>