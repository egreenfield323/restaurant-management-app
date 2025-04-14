<template>
    <img class="logo" src="../assets/restaurant-logo.png" />
    <h1>Sign Up</h1>
    <div class="register">
        <input type="text" placeholder="Enter Name" />
        <input type="text" placeholder="Enter Email" />
        <input type="password" placeholder="Enter Password" />
        <button>Sign Up</button>
    </div>
</template>

<script>
export default {
    name: 'SignUp'
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