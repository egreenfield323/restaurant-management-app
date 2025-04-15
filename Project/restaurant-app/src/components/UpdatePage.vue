<template>
    <PageHeader />
    <h1>Welcome to the update restaurant page.</h1>
    <form class="add">
        <input type="text" name="name" placeholder="Enter name" v-model="restaurant.name" />
        <input type="text" name="address" placeholder="Enter address" v-model="restaurant.address" />
        <input type="text" name="contact" placeholder="Enter contact" v-model="restaurant.contact" />
        <button type="button" v-on:click="updateRestaurant">Update</button>
    </form>
</template>

<script>
import PageHeader from './PageHeader.vue';
import axios from 'axios';
export default {
    name: 'UpdatePage',
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
    async mounted() {
        let user = localStorage.getItem('user-info');
        if (!user) {
            this.$router.push({ name: 'SignUp' });
        }

        const result = await axios.get('http://localhost:3000/restaurants/' + this.$route.params.id);
        this.restaurant = result.data
    }
}
</script>