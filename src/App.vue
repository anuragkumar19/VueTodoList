<template>
    <div id="app">
        <Navbar />
        <div class="container">
            <router-view />
        </div>
    </div>
</template>

<script>
import Navbar from "./components/Navbar";

export default {
    name: "app",
    components: {
        Navbar,
    },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto+Slab:wght@100;200;300;400;500;600;700;800;900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Sansita+Swashed:wght@300;400;500;600;700;800;900&display=swap");

* {
    font-family: "Roboto Slab", serif;
}

.cursive-style {
    font-family: "Sansita Swashed", cursive;
}

.my-2 {
    margin-top: 1rem;
    margin-bottom: 1rem;
}

i,
label {
    user-select: none;
}
</style>
