<template>
    <div class="nav-fixed">
        <nav class="blue darken-3">
            <div class="container">
                <div class="nav-wrapper">
                    <router-link to="/" class="brand-logo left">
                        <i class="material-icons" style="font-size: 3rem"
                            >event_note</i
                        >
                    </router-link>
                </div>
                <ul class="right">
                    <li><router-link to="/">Home</router-link></li>
                    <li><router-link to="/about">About</router-link></li>
                </ul>
            </div>
        </nav>
    </div>
</template>

<script>
export default {
    name: "Navbar",
};
</script>

<style></style>
