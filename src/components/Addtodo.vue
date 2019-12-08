<template>
    <div class="inputToDoElem">
        <form @submit.prevent = "readInput">
            <label>Please write you text</label>
            <div class="input-field" >
                <textarea  v-model="inputToDo" class="materialize-textarea"></textarea>
            </div>
            <button class="btn-floating btn-large waves-effect waves-light red" type="submit">+</button>
        </form>

    </div>
</template>
<script>
    export default {
        data(){
            return {
                inputToDo:''
            }
        },
        methods:{
            readInput(){
                if(this.inputToDo.trim()){
                    const newTodo = {
                        id:Date.now(),
                        title:this.inputToDo,
                        completed:false
                    };
                    this.$emit('add-todo',newTodo)
                    this.inputToDo = '';
                }
            }
        }
    }
</script>
<style scoped>
    .inputToDoElem{
        text-align: center;
    }
    .inputToDoElem textarea{
        text-align: center;
        max-width: 300px;
    }
    button{
        padding: 50px;
        margin-bottom: 50px;
    }

</style>