<template>
    <PageHeader />
    <h1>Welcome to the add restaurant page.</h1>
</template>

<script>
import PageHeader from './PageHeader.vue';
export default {
    name: 'AddPage',
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