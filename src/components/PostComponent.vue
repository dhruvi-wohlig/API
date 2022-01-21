<template>
    <div id="app">
        <h1>Post Component</h1>
        <form @submit="submitData" method="post">
            <input type="text" placeholder="title" v-model="comment.title" /><br><br>
            <input type="text" placeholder="author" v-model="comment.author" /><br><br>
            <button type="submit">Submit</button>
        </form>
    </div>
</template>
<script>
import Vue from 'vue';
import VueAxios from 'vue-axios';
import axios from 'axios';
Vue.use(VueAxios,axios)
export default {
    name: "PostComponent",
    data(){
        return {
            comment: {
                title: null,
                author: null
            }
        }
    },
    methods: {
        submitData(e){
            this.axios.post('http://localhost:3000/posts',this.comment).then((resp)=>{
                console.warn("resp",resp)
            })
            console.warn(this.comment);
            e.preventDefault();
        }
    }
};
</script>
