<template>
    <PageHeader />
    <h1>Welcome to the add restaurant page.</h1>
    <form class="add">
        <input type="text" name="name" placeholder="Enter name" v-model="restaurant.name" />
        <input type="text" name="address" placeholder="Enter address" v-model="restaurant.address" />
        <input type="text" name="contact" placeholder="Enter contact" v-model="restaurant.contact" />
        <button type="button" v-on:click="addRestaurant">Add</button>
    </form>
</template>

<script>
import PageHeader from './PageHeader.vue';
import axios from 'axios';
export default {
    name: 'AddPage',
    components: {
        PageHeader
    },
    data() {
        return {
            restaurant: {
                name: '',
                address: '',
                contact: ''
            }
        }
    },
    methods: {
        async addRestaurant() {
            const result = await axios.post("http://localhost:3000/restaurants", {
                name: this.restaurant.name,
                address: this.restaurant.address,
                contact: this.restaurant.contact
            });
            if (result.status === 201) {
                this.$router.push({ name: 'HomePage' });
            }
        }
    },
    mounted() {
        let user = localStorage.getItem('user-info');
        if (!user) {
            this.$router.push({ name: 'SignUp' });
        }
    }
}
</script>