<template>
    <div>
        <h1>User Component</h1>
        <div align="center">
            <table border="1px">
                <tr>
                    <td>Id</td>
                    <td>Title</td>
                    <td>Author</td>
                    <td>Action</td>
                </tr>
                <tr v-for="item in users" v-bind:key="item.id">
                    <td>{{ item.id }}</td>
                    <td>{{ item.title }}</td>
                    <td>{{ item.author }}</td>
                    <td><button v-on:click="deleteUser(item.id)">Delete</button></td>
                </tr>
            </table>
        </div>
    </div>
</template>
<script>
    import Vue from 'vue';
    import VueAxios from 'vue-axios';
    import axios from 'axios';
    Vue.use(VueAxios,axios)
    export default{
        name: "Users",
        data(){
            return{
                users: null
            }
        },
        methods:{
            getUsers(){
                this.axios.get('http://localhost:3000/posts').then((response) => {
                console.warn(response)
                this.users = response.data   
                })
            },
            deleteUser(id){
                this.axios.delete('http://localhost:3000/posts/'+ id).then((response) => {
                    console.warn(response)
                    this.getUsers()
                })
            }
        },
        mounted(){
            this.getUsers()
        }
    }
</script>
