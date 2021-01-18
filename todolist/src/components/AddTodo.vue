<template>
    <div>
        <form @submit="addTodo">
            <input 
                type="text" 
                v-model="title" 
                name='title' 
                placeholder="Adicionar tarefa..."
            >
            <button type="submit" value='submit' class='btn'>Submit</button>
        </form>
    </div>
</template>

<script>
export default {
    name: "AddTodo",
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addTodo(event) {
            event.preventDefault()
            const newTodo = {
                id: Date.now(),
                title: this.title,
                completed: false
            }
            // //send up to parent
            this.$emit('add-todo', newTodo)
            this.title = ''
        }
    }

}
</script>

<style scoped>
    form {
        display: flex;
        height: 40px;
    }
    input[type='text'] {
        padding: 5px;
        flex: 10; /*q isso*/
    }
    input[type='submit'] {
        flex: 2; /*q isso!*/
    }
</style>