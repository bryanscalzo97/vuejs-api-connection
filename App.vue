<template>
    <div>
        <table>
            <tbody>
                <tr v-for="todo in todos" :key="todo.id">
                    <td>{{ todo.id }}</td>
                    <td>{{ todo.completed }}</td>
                    <td>{{ todo.title }}</td>
                    <td>{{ todo.userId }}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    data() {
        return {
            todos: null
            }
    },
    mounted(){
        console.log('Hola mundo desde mounted')
        this.getTodos();
    },
    methods: {
        getTodos(){
            console.log('aca va el codigo de get todos')
            axios.get('https://jsonplaceholder.typicode.com/todos')
            .then( response => {
                console.log(response)
                this.todos = response.data
            })
            .catch( e=> console.log(e))
        },
        
        
        
    },
}
</script>
<style>

</style>
