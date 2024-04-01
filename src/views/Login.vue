<script>
export default {
    data(){
        return{
            username: '',
            password: ''
        }
    },
    methods:{
        login(){
            window.user = this.username;
            const redirectPath = this.$route.query.redirect || '/protected';
            this.$router.push(redirectPath);
        }
    }
}
</script>

<template>
    <div class="login">
        <form class="form" @submit.prevent="login">
            <h1>Login</h1>
            <label for="username">Username</label>
            <input type="text" class="input" name="username" v-model="username">
            
            <label for="password">Password</label>
            <input type="text" class="input" name="password" v-model="password">
        
            <button class="btn">Login</button>
        </form>
    </div>
</template>