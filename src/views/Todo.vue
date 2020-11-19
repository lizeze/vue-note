<template>

    <div>
        <input type="text" v-model="inputText">
        <button @click="addTodo">增加</button>
        <toto-list :list="list" @deleteHandle="deleteHandle"></toto-list>

    </div>
</template>

<script>
    import TotoList from "../components/TotoList";

    export default {
        name: 'todo',
        components: {TotoList},
        data: () => {
            return {
                inputText: '',
                list: []
            }
        },
        methods: {
            addTodo: function () {
                this.list.push({
                    key: Date.now(),
                    text: this.inputText
                })
                this.inputText=''
            },
            deleteHandle: function (key) {
                this.list = this.list.filter(t => t.key != key)
            }
        }
    }
</script>

<style>

</style>
