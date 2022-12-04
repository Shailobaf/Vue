<template>
    <div class="app">
        <form>
            <h4>Создание поста</h4>
            <input v-bind:value="title" @input="inputTitle" type="text" placeholder="Название">
            <input v-bind:value="body" class="input" type="text" placeholder="Описанние">
            <button class="btn" @click="createPost">Создать</button>
        </form>
    </div>
    <div class="post" v-for="post in post" v-bind:key="post.id">
        <div><strong>Название:</strong>{{post.title}}</div>
        <div><strong>Описание:</strong>{{post.body}}</div>
    </div>
</template>
<script>
export default {
    data (){
        return {
           post: [
            {id: 1, title: 'Javacript', body: 'Описание поста'},
            {id: 2, title: 'Javacript2', body: 'Описание поста2'},
            {id: 3, title: 'Javacript3', body: 'Описание поста3'},  
            {id: 4, title: 'Javacript4', body: 'Описание поста4'}, 
        ],
        title: "",
        body: ""
        }
    },
    methods: {
        createPost(){
        },
        inputTitle(event){
console.log(event);
        }
    }
}
</script>
<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.post {
    padding: 15px;
    border: 2px solid rgb(94, 2, 255);
    margin-top: 5px;
}
.input{
    width: 100%;
    border:1px solid rgb(94, 2, 255);
    padding: 10px 15px;
    margin-top: 15px;
}
.app {
    padding: 20px;
}
form {
    display: flex;
    flex-direction: column;
}
.btn{
    padding: 10px 15px;
    margin-top: 15px;
    align-self: flex-end;
    background: none;
    color: rgb(94, 2, 255);
}
</style>