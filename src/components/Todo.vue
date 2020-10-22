<template>
    <tr
        :class="{ 'green lighten-3': todo.completed }"
        @dblclick="toggleCompleted"
    >
        <td>{{ todo.title }}</td>
        <td>{{ todo.createdAt }}</td>
        <td>
            <button
                @click="$emit('delete-todo', todo.id)"
                class="btn-flat red darken-2 white-text"
            >
                <i class="material-icons">delete</i>
            </button>
        </td>
    </tr>
</template>

<script>
export default {
    name: "Todo",
    props: ["todo"],
    methods: {
        toggleCompleted() {
            this.todo.completed = !this.todo.completed;
            const todos = JSON.parse(localStorage.todos);
            let obj = todos.find((t) => t.id == this.todo.id);

            if (obj) {
                let i = todos.indexOf(obj);
                if (i !== -1) {
                    todos[i] = this.todo;
                    localStorage.todos = JSON.stringify(todos);
                }
            }
        },
    },
};
</script>

<style>
</style>