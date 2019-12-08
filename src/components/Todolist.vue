<template>
    <div>
        <li class="liItem">
            <span v-bind:class="{done:td.completed}">

                {{td.title}}

            </span>

        </li>
        <br>
    </div>
</template>

<script>
    export default {
        props: {
            td: {
                type: Object,
                required: true
            }
        }
    }
</script>
<style scoped>
    .liItem input{
        margin-right: 100px;
    }
    button{

        margin-left: 100px;
    }
.done{
    text-decoration: line-through;
}
</style>