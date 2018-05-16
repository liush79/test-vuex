<template>
    <div id="get-todo" class="container input-group">
        <input class="form-control"
               :value="newTodo_local"
               @change="getTodo_local"
               placeholder="I need to...">
        <span class="input-group-btn">
            <button class="btn btn-primary" @click="addTodo_local">Add Todo</button>
        </span>
    </div>
</template>
<script>
    export default{
        methods: {
            getTodo_local(e){
                this.$store.dispatch('getTodo', e.target.value)
            },
            addTodo_local(){
                this.$store.dispatch('addTodo')
                this.$store.dispatch('clearTodo')
            }
        },
        computed: {
            newTodo_local(){
                return this.$store.getters.newTodo
            }
        }
}
</script>