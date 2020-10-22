<template>
    <section class="my-2">
        <h4 class="cursive-style center-align">All Todos</h4>
        <div class="divider"></div>

        <div class="card">
            <div class="card-content">
                <div style="overflow: auto">
                    <table>
                        <thead>
                            <tr>
                                <th>Title</th>
                                <th>Created At</th>
                                <th>Actions</th>
                            </tr>
                        </thead>

                        <tbody>
                            <Todo
                                v-for="todo in todos"
                                :key="todo.id"
                                :todo="todo"
                                v-on:delete-todo="$emit('delete-todo', todo.id)"
                            />
                        </tbody>
                    </table>
                </div>
            </div>
        </div>

        <p style="font-size: 12px" class="grey-text text-lighten-1">
            * Double Click to toggle completed
        </p>
    </section>
</template>

<script>
import Todo from "./Todo";

export default {
    name: "AllTodo",
    components: {
        Todo,
    },
    props: ["todos"],
};
</script>

<style>
</style>