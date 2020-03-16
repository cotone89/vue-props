<template>
    <div id="app">
        <h1>Crear una nueva tarea</h1>
        Tarea: <input type="text" id="inputTarea" />
        <button @click="agregarTarea">Crear</button>

        <ul>
            <li v-for="(tarea,index) in listaTareas">
                <Hijo :tarea="tarea" :index="index" @eliminarTareaHijo="eliminarTareaPadre"></Hijo>
            </li>
        </ul>

        
    </div>
</template>
<script>
    import Hijo from './components/Hijo.vue';   

    export default {
        components: { Hijo },
        data() {
                return {
                    listaTareas: [],
                    tarea : ""
		        }
        },
        methods: {
            agregarTarea() {
                this.tarea = $("#inputTarea").val();
                this.listaTareas.push(this.tarea);//se agrega tarea
            },
            eliminarTareaPadre(index) {
                console.log("llega al padre el index-- " + index);
                this.listaTareas.splice(index,1); // se elimina tarea

            }
        }
    };
</script>
<style>
    #app {
        font-size: 25px;
        font-family: 'Calibri', sans-serif;
        color: darkblue;
        background: lightblue;
    }
</style>