<template>
    <div class="container">
        <div class="row justify-content-center">
            <not-found></not-found>
        </div>
    </div>
</template>

<script>
export default {
    computed: {
        username() {
            // We will see what `params` is shortly
            return this.$route.params.username;
        }
    },
    methods: {
        goBack() {
            window.history.length > 1
                ? this.$router.go(-1)
                : this.$router.push("/");
        }
    }
};
</script>
