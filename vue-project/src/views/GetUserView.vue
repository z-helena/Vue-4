<script lang="ts">
export default {
    data() {
        return {
            user: {
                firstName: "",
                lastName: "",
                email: ""
            }

        }
    },

    methods: {
        async fetchUser() {
            const response = await fetch('https://hm-bookstore-api.onrender.com/user/3', {
                method: 'GET'
        });
        const data = await response.json();
        this.user = data;
    }
}
}
</script>

<template>
    <button @click="fetchUser">Get user </button>
    <p>{{ user.firstName }}</p>
    <p>{{ user.lastName }}</p>
    <p>{{ user.email }}</p>

</template>
