<template>
    <header>
        <ul>
            <li>
                <NuxtLink to="/">Home</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/about">About</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/contact">Contact</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/users">Users</NuxtLink>
            </li>
        </ul>
    </header>
</template>

<style scoped>

    header {
        background-color: lightgoldenrodyellow;
        padding: 20px;
    }
    header ul {
        display: inline-flex;
    }
    header li {
        padding: 15px;
        list-style: none;
    }

</style>