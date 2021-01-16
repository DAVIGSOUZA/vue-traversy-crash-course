<template>
    <div class='todo-item' v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{todo.title}}
            <button class='del' @click="$emit('del-todo', todo.id)" >X</button>
        </p>
    </div>
</template>

<script>
export default {
    name: 'TodoItem',
    props: ['todo'],
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed
        }
    }
}
</script>

<style scoped>
    .todo-item {
        background: whitesmoke;
        padding: 10px;
        border-bottom: 1px gray dotted;
    }

    .is-complete {
        text-decoration: line-through;
    }

    .del {
        background: lightcoral;
        color: whitesmoke;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }

</style>