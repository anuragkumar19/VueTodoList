<template>
    <div>
        <AddTodo v-on:addTodo="addTodo" />
        <AllTodo :todos="todos" v-on:delete-todo="deleteTodo" />
    </div>
</template>

<script>
import AddTodo from "../components/AddTodo";
import AllTodo from "../components/AllTodo";

export default {
    name: "Home",
    components: {
        AddTodo,
        AllTodo,
    },

    data() {
        return {
            todos: [
                {
                    id: 1,
                    title: "Title 1",
                    completed: false,
                    createdAt: "12-10-2020",
                },
                {
                    id: 2,
                    title: "Title 2",
                    completed: true,
                    createdAt: "12-10-2020",
                },
                {
                    id: 3,
                    title: "Title 3",
                    completed: true,
                    createdAt: "12-10-2020",
                },
            ],
        };
    },

    methods: {
        deleteTodo(id) {
            this.todos = this.todos.filter((todo) => todo.id != id);
            localStorage.todos = JSON.stringify(this.todos);
        },
        addTodo(todo) {
            const newTodos = this.todos;
            newTodos.push(todo);
            localStorage.todos = JSON.stringify(newTodos);

            this.todos = JSON.parse(localStorage.todos);
        },
    },

    created() {
        if (!localStorage.todos) {
            localStorage.todos = JSON.stringify([]);
        }

        this.todos = JSON.parse(localStorage.todos);
    },
};
</script>
