<template>
    <PageHeader />
    <h1>Hello {{ this.name }}, welcome to the home page.</h1>
</template>

<script>
import PageHeader from './PageHeader.vue';
export default {
    name: 'HomePage',
    data() {
        return {
            name: ''
        }
    },
    components: {
        PageHeader
    },
    mounted() {
        let user = localStorage.getItem('user-info');
        this.name = JSON.parse(user).name;
        if (!user) {
            this.$router.push({ name: 'SignUp' });
        }
    }
}
</script>