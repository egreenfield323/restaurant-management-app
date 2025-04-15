<template>
    <PageHeader />
    <h1>Welcome to the home page.</h1>
</template>

<script>
import PageHeader from './PageHeader.vue';
export default {
    name: 'HomePage',
    components: {
        PageHeader
    },
    mounted() {
        let user = localStorage.getItem('user-info');
        if (!user) {
            this.$router.push({ name: 'SignUp' });
        }
    }
}
</script>