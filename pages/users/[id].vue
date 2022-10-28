<template>
    <div>
        <p v-if="loading">loading.....</p>
        <h2>{{ user.name }}</h2>
        <p>{{ user.email }}</p>
        <p>{{ user.phone }}</p>
        <NuxtLink to="/users">Back to Users</NuxtLink>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                user:{},
                loading:false,
            }
        },
        created () {
            const id = this.$route.params.id;
            
            this.loading = true
            fetch(`https://jsonplaceholder.typicode.com/users/${id}`)
                .then(response => response.json())
                .then(json => {
                    this.user = json;
                    this.loading = false
                });
        }
    }
</script>