<template>
    <div class="content">
        <h1 class="title">ToDo list - Vuejs</h1><br>
        <input class="box_coments" type="text" v-model="coments" placeholder="Digite algo">
        <button class="enviar" @click="EnviarComentario">Enviar</button> 

        <p class="list_coments" v-show="add_coment" v-for="(li, i) in listMessage" v-bind:key="li"> 
            {{ li }}
            <button
            @click="RemoveComent(del, i)" class="delete_coment">Del</button>
        </p>
        <button v-show="remove_coment" class="Reset" @click="DeletarTodos">Reset</button>
    </div>
</template>







<script>
    export default {
        name: 'TodosComents',
        data() {
            return{
            listMessage: [],
            add_coment: true,
            remove_coment: false,
            }
        },
        methods: {
            EnviarComentario (a) {
                a.preventDefault()
                this.li = this.coments
                this.listMessage.unshift(this.li)
                this.coments = ''
                if(this.remove_coment === false){
                    this.remove_coment = !this.remove_coment
                    this.delete_one = !this.delete_one
                }
            },

            DeletarTodos(b) {
                b.preventDefault()
                this.listMessage = []
                this.coments = ''
                if(this.remove_coment === true){
                    this.remove_coment = !this.remove_coment
                    this.delete_one = !this.delete_one
                }
            },

            RemoveComent(del, i) {
                this.coments = ''
                this.listMessage.splice(i, 1)
                if (this.listMessage.length === 0) {
                    this.remove_coment = !this.remove_coment
                }
                console.log(i);
            }
        }
    }






</script>

<style>
    body{
        background-color: rgb(3, 87, 79);
    }
    .title{
        font-family:'Times New Roman', Times, serif;
        font-size: 50px;
        color: rgb(189, 233, 231);
        margin-left: 40%;
        margin-right: 40%;
        border-bottom: solid;
        border-color: rgb(2, 28, 28);
    }

    .box_coments{
        height: 50px;
        width: 500px;
        border-top-left-radius: 10px;
        border-bottom-left-radius: 10px;
        border: none;
        font-size: 25px;
    }

    .enviar{
        height: 52px;
        width: 100px;
        border: none;
        border-top-right-radius: 10px;
        border-bottom-right-radius: 10px;
        background-color: aqua;
        font-size: 25px;
    }

    .list_coments{
        width: 600px;
        height: 60px;
        background-color: rgb(0, 5, 26, 0.7);
        position: relative;
        left: 652.5px;
        font-size: 35px;
        color: white;
        border-radius: 5px;
        margin-top: 20px;
        margin-bottom: 20px;
    }

    .Reset{
        height: 52px;
        width: 100px;
        border: none;
        border-radius: 10px;
        background-color: aqua;
        font-size: 25px;
    }

    .delete_coment{
        position: absolute;
        height: 60px;
        width: 60px;
        right: 0px;
        background-color: aqua;
    }


</style>