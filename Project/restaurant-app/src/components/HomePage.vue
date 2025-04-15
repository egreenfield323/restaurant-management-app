<template>
    <PageHeader />
    <h1>Hello {{ this.name }}, welcome to the home page.</h1>
    <div class="table">
        <table border="1px">
            <tr>
                <td><b>Id</b></td>
                <td><b>Name</b></td>
                <td><b>Contact</b></td>
                <td><b>Address</b></td>
                <td><b>Actions</b></td>
            </tr>
            <tr v-for="item in restaurant" :key="item.id">
                <td>{{ item.id }}</td>
                <td>{{ item.name }}</td>
                <td>{{ item.contact }}</td>
                <td>{{ item.address }}</td>
                <td>
                    <router-link :to="'/update/' + item.id">Update</router-link>
                    <button v-on:click="deleteRestaurant(item.id)">Delete</button>
                </td>
            </tr>
        </table>
    </div>
</template>

<script>
import PageHeader from './PageHeader.vue';
import axios from 'axios';
export default {
    name: 'HomePage',
    data() {
        return {
            name: '',
            restaurant: [],
        }
    },
    components: {
        PageHeader
    },
    methods: {
        async deleteRestaurant(id) {
            let result = await axios.delete('http://localhost:3000/restaurants/' + id);
            if (result.status === 200) {
                this.loadData()
            }
        },
        async loadData() {
            let user = localStorage.getItem('user-info');
            this.name = JSON.parse(user).name;
            if (!user) {
                this.$router.push({ name: 'SignUp' });
            }
            let result = await axios.get('http://localhost:3000/restaurants');
            this.restaurant = result.data;
        }
    },
    async mounted() {
        this.loadData()
    }
}
</script>

<style>
.table {
    display: flex;
    justify-content: center;
    margin-top: 30px;
}

table {
    border-collapse: collapse;
    width: 80%;
    max-width: 900px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
    font-family: Arial, sans-serif;
    background-color: #fff;
    border-radius: 10px;
    overflow: hidden;
}

th, td {
    padding: 12px 16px;
    text-align: left;
}

th {
    background-color: #f4f4f4;
    font-weight: bold;
    border-bottom: 2px solid #ddd;
}

td {
    border-bottom: 1px solid #eee;
}

tr:hover {
    background-color: #f9f9f9;
}

button {
    margin-left: 10px;
    padding: 6px 10px;
    background-color: #e74c3c;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #c0392b;
}

router-link {
    color: #3498db;
    text-decoration: none;
}

router-link:hover {
    text-decoration: underline;
}
</style>