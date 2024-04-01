<script>
export default {
    data(){
        return{
            username: window.user
        }
    },
    methods: {
        logout(){
            window.user = null
            this.$router.push({name: 'Home'})
        }
    }
}
</script>

<template>
    <div>
        <h1>Greetings, {{ username }}</h1>
        <button class="btn" @click="logout">LogOut</button>
        <router-link :to="{name: 'invoices'}">
            <button>Invoices</button>
        </router-link>
    </div>
</template>