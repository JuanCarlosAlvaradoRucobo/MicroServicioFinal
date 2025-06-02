<template>
    <div>
        <header class="shadow-sm bg-red-100">
            <nav class="container mx-auto p-10 flex justify-between ">
               <NuxtLink to="/" class="font-bold">Mi guru</NuxtLink> 
                <ul class="flex gap-4">
                    <il><NuxtLink to="/">Index</NuxtLink></il>
                    <il><NuxtLink to="/Home">Home</NuxtLink></il>
                    <il><NuxtLink to="/Login">Login</NuxtLink></il>
                    <il><NuxtLink to="/Dashboard">Dashboard</NuxtLink></il>
                </ul>
            </nav>
        </header>


        <div class="container mx-auto p-4">
            <slot />
        </div>
    </div>
</template>
<style scoped>
    .router-link-exact-active {
        color: #12b488;
    }
</style>