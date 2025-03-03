<script>
export default {
    data() {
        return {
            user: {
                first_name: "",
                last_name: "",
                email: ""
            }

        }
    },

    methods: {
        async fetchUser() {
            const response = await fetch('https://hm-bookstore-api.onrender.com/user/3');
            console.log(response);

            const data = await response.json();
            this.user = data;
        }
    }
}
</script>

<template>
    <p>{{ user.first_name }}</p>
    <p>{{ user.last_name }}</p>
    <p>{{ user.email }}</p>

</template>
