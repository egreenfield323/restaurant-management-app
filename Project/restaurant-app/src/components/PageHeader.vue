<template>

    <div class="nav">
        <router-link to="/">Home</router-link>
        <router-link to="/add">Add Restaurant</router-link>
        <a v-on:click="logout" href="#">Logout</a>
    </div>

</template>

<script>
export default {
    name: 'PageHeader',
    methods: {
        logout() {
            localStorage.clear();
            this.$router.push({ name: 'LogIn' })
        }
    }
}
</script>

<style>
.nav {
    background-color: #333;
    overflow: hidden;
}

.nav a {
    float: left;
    color: aliceblue;
    padding: 14px 16px;
    text-align: center;
    font-size: 17px;
    text-decoration: none;
    margin-right: 6px;
}

.nav a:hover {
    background-color: white;
    color: #333;
}
</style>