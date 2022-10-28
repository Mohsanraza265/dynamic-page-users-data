<template>
    <div>
        <h2>{{title}}</h2>
        <ul>
            <p v-if="loading">loading.....</p>
            <li v-for="user in users" :key="user.id">
                <NuxtLink :to="`/users/${user.id}`">{{ user.name }}</NuxtLink>
            </li>
        </ul>
    </div>

</template>

<script>

export default
    {
        data() {
            return {
                title: "User Listing",
                users: [],
                loading:false,
            };
        },
        methods:{
            fetchData(){
                this.loading = true
                fetch("https://jsonplaceholder.typicode.com/users")
                .then(response => response.json())
                .then(json => {
                    this.users = json;
                    this.loading = false
                });
            }
        },
        created() {
         this.fetchData()   
        }
    };

</script>