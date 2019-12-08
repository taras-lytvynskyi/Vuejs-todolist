<template>
    <div class="allItem">

        <ul v-show="showItems">
            <h4>You to do list!</h4>
            <Addtodo @add-todo = "addToDo"/>
            <Todolist
                    v-for="todo in todoItems"
                    :key="todo.id"
                    v-bind:td="todo"
            />
        </ul>

        <form @submit.prevent="onSubmit" v-show="showLogin">
            <div class="textTitle">
                <h3>Hello!</h3>
                <label>Please login.</label>
            </div>
            <p>Login</p>
            <input type="text" v-model="login" placeholder="Login">
            <p>Password</p>
            <input class="validate" type="password" v-model="password" placeholder="Password">
            <br>
            <div style="color: #E53935" v-show = "showWrongItem">
                Wrong user!
            </div>
            <button type="submit" class="waves-effect waves-light btn grey darken-4"> Submit!</button>
            <footer>
                <br>
                <a style="cursor: pointer" id="Dark" v-on:click="Dark"> Dark | </a>
                <a style="cursor: pointer" id="Light" v-on:click="Light"> Light </a>

            </footer>
        </form>


    </div>

</template>
<script>
    import Todolist from "./Todolist";
    import Addtodo from "./Addtodo";

    export default {
        components: {
            Todolist,
            Addtodo
        },
        data() {
            return {
                login: '',
                password: '',
                showLogin: true,
                showItems: false,
                showWrongItem: false,
                todoItems: [
                    {id: 1, title: 'To do 1', completed: false},
                    {id: 2, title: 'To do 2', completed: false},
                    {id: 3, title: 'To do 3', completed: false},
                    {id: 4, title: 'To do 4', completed: false},
                    {id: 5, title: 'To do 5', completed: false}
                ]
            }
        },
        methods: {
            Dark() {
                document.body.style.background = "#212121";
                document.body.style.color = "white";
            },
            Light(){
                document.body.style.background = "white" ;
                document.body.style.color = "#212121";
                document.body.style.input = "black"
            },
            addToDo(todo){
                this.todoItems.push(todo);
            },
            onSubmit() {
                if (this.login.trim() && this.password.trim()) {
                    if (this.login === "root" && this.password === "root") {
                        this.showItems = true;
                        this.showLogin = false;
                    } else {
                        this.showWrongItem = true;
                    }
                }
            }
        }
    }

</script>
<style scoped>
    .textTitle {
        padding-bottom: 50px;
    }

    .allItem a{
        color: black;
    }
    .allItem {
        text-align: center;
        margin-top: 10%;
    }

    input {
        text-align: center;
        max-width: 20%;
    }

    button {
        margin-top: 50px;
    }
</style>