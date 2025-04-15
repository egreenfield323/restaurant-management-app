<template>
    <img class="logo" src="../assets/restaurant-logo.png" />
    <h1>Log in</h1>
    <div class="login">
        <input type="text" v-model="email" placeholder="Enter Email" />
        <input type="password" v-model="password" placeholder="Enter Password" />
        <button v-on:click="login">Log In</button>
        <p>
            Already a user?
            <router-link to="/sign-up">Login</router-link>
        </p>
    </div>

</template>

<script>
import axios from 'axios';
export default {
    name: 'LogIn',
    data() {
        return {
            email: '',
            password: ''
        }
    },
    methods: {
        async login() {
            let result = await axios.get(
                `http://localhost:3000/users?email=${this.email}&password=${this.password}`
            )
            if (this.email != '' && this.password != '' && result.status === 200 && result.data.length > 0) {
                result.data.forEach(element => {
                    if (element.email === this.email && element.password === this.password) {
                        localStorage.setItem("user-info", JSON.stringify(result.data[0]))
                        this.$router.push({ name: 'HomePage' });
                    }
                });
            }
        }
    },
    mounted() {
        let user = localStorage.getItem('user-info');
        if (user) {
            this.$router.push({ name: 'HomePage' });
        }
    }
};

</script>