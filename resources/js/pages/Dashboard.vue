<template>
    <div>
        Welcome {{ name }} {{role}}
    </div>
</template>

<script>
export default {
    name: "Dashboard",
    data() {
        return {
            name: null,
            role:""
        }
    },
    created() {
        console.log(window.Laravel);
        if (window.Laravel.user) {
            this.name = window.Laravel.user.name
            this.role = window.Laravel.role
        }
    },
    // beforeRouteEnter(to, from, next) {
    //     if (!window.Laravel.isLoggedin) {
    //         window.location.href = "/";
    //     }
    //     next();
    // }
}
</script>