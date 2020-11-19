<template>

     <div>

         <ul>

             <li v-for="item in this.list":key="item.key">

                  {{item.text}} <button @click="deleteHandle(item.key)">删除</button>
             </li>
         </ul>

     </div>
</template>

<script>
    export default {
        name: 'TotoList',
        props:{

            list:{
                type:Array,
                default(){
                    return[]
                }
            }
        },
        methods:{
            deleteHandle:function (key) {
                 this.$emit('deleteHandle',key)
            }
        }

    }
</script>

<style scoped>

</style>
