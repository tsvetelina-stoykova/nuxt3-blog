<template>
    <header class="w-full h-16">
        <nav class="bg-fuchsia-900 py-2 md:py-4">
            <div class="container px-4 mx-auto md:flex md:items-center">
                <div class="flex justify-between items-center">
                    <NuxtLink to="/" class="font-bold text-xl  text-white">Demo</NuxtLink>
                    <button class="border border-solid border-white-600 px-3 py-1 rounded text-white opacity-50 hover:opacity-75 md:hidden" id="navbar-toggle">
                        <i class="fas fa-bars"></i>
                    </button>
                </div>

                <div class="hidden md:flex flex-col md:flex-row md:ml-auto mt-3 md:mt-0" id="navbar-collapse">
                    <NuxtLink to="/home" class="p-2 lg:px-4 md:mx-2 text-white rounded hover:bg-gray-200 hover:text-fuchsia-900 transition-colors duration-300">Home</NuxtLink>
                    <NuxtLink to="/posts" class="p-2 lg:px-4 md:mx-2 text-white rounded hover:bg-gray-200 hover:text-fuchsia-900 transition-colors duration-300">Posts</NuxtLink>
                </div>
            </div>
        </nav>
    </header>
</template>