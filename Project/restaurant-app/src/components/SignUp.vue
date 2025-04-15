<template>
    <img class="logo" src="../assets/restaurant-logo.png" />
    <h1>Sign Up</h1>
    <div class="register">
        <input type="text" v-model="name" placeholder="Enter Name" />
        <input type="text" v-model="email" placeholder="Enter Email" />
        <input type="password" v-model="password" placeholder="Enter Password" />
        <button v-on:click="signUp">Sign Up</button>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    name: 'SignUp',
    data() {
        return {
            name: '',
            password: '',
            email: ''
        }
    },
    methods: {
        async signUp() {
            let result = await axios.post("http://localhost:3000/users", {
                name: this.name,
                password: this.password,
                email: this.email
            });

            console.log(result);
            if (result.status === 201) {
                localStorage.setItem("user-info", JSON.stringify(result.data));
                this.$router.push({ name: 'HomePage' });
            }
        }
    },
    mounted() {
        let user = localStorage.getItem('user-info');
        if (user) {
            this.$router.push({ name: 'HomePage' });
        }
    }
}
</script>

<style>
.logo {
    width: 150px
}

.register input {
    width: 300px;
    height: 40px;
    padding-left: 20px;
    display: block;
    margin: auto auto 30px auto;
    border: 1px solid rgb(0, 0, 82);
    border-radius: 25px;
}

.register button {
    width: 130px;
    height: 40px;
    border: 1px solid rgb(0, 0, 82);
    background-color: rgb(0, 0, 82);
    color: #fff;
    cursor: pointer;
    border-radius: 25px;
}

.register button:hover {
    width: 128px;
    background-color: rgb(0, 0, 21);
    border: 3px solid white;
}
</style>