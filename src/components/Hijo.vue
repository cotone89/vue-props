<template>
    <div class="hellovue">
       {{index+1}} - {{tarea}}<button class="hijo__boton" @click="eliminarTarea(index)">Eliminar</button>
    </div>
</template>
<script>
    export default {
        name: 'hijo',
        props: {
            tarea: String,
            index: Number
        },
        methods: {
            eliminarTarea(index) {
                console.log("el index que voy a enviar es-- " + index);
                this.$emit('eliminarTareaHijo', index); //se envía a papá
            }
        }
    };
</script>
<style scoped>
    .hellovue {
        display: inline;
    }

    .helloimg {
        width: 25%;
        height: 25%;
    }
    .hijo__boton{
        margin-left: 10px;
    }
</style>