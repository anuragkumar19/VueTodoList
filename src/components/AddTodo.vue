<template>
    <section class="my-2">
        <div class="card">
            <div class="card-content">
                <form @submit.prevent="addTodo">
                    <div class="row">
                        <div class="input-field col s12">
                            <i class="material-icons prefix">event</i>
                            <input
                                v-model="title"
                                id="title-input"
                                type="text"
                            />
                            <label for="title-input">Title</label>
                        </div>
                    </div>
                    <div class="right-align">
                        <button type="submit" class="btn blue darken-3">
                            <i class="material-icons left">add_box</i>Create
                        </button>
                    </div>
                </form>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: "AddTodo",
    data() {
        return {
            title: "",
        };
    },
    methods: {
        addTodo() {
            this.$emit("addTodo", {
                title: this.title,
                completed: false,
                id: Date.now(),
                createdAt: new Date().toLocaleDateString(),
            });

            this.title = "";
        },
    },
};
</script>

<style>
</style>