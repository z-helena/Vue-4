<script lang="ts">
export default {
    data() {
        return {
            user: {
                firstName: "Alexa",
                lastName: "Wang",
                email: "alexawang@gmail.com"
            }

        }
    },

    methods: {
        async createUser() {

            const user = {
                firstName: this.user.firstName,
                lastName: this.user.lastName,
                email: this.user.email
            };
            const response = await fetch('https://hm-bookstore-api.onrender.com/user', {

                method: 'POST',
                body: JSON.stringify(user)

            });
            const data = await response.json();
            this.user = data;
        }
    }
}
</script>


<template>
    <p>{{ user.firstName }}</p>
    <p>{{ user.lastName }}</p>
    <p>{{ user.email }}</p>

</template>