<template>
    <img class="logo" src="../assets/restaurant-logo.png" />
    <h1>Log in</h1>
    <div class="login">
        <input type="text" v-model="email" placeholder="Enter Email" />
        <input type="password" v-model="password" placeholder="Enter Password" />
        <button>Log In</button>
        <p>
            Already a user?
            <router-link to="/sign-up">Login</router-link>
        </p>
    </div>

</template>

<script>

export default {
    name: 'LogIn'
}

</script>