<template>
    <div id="form">
        <label for="tarea">Ingresa el nombre de una tarea</label>
        <input v-model="tarea" type="text" id="tarea">
        <button @click="addTarea" class="btn btn-primary">Agregar Tarea</button>
        <!-- <button @click="removeTarea" class="btn btn-primary">Remover Tarea</button> -->
        <div v-for="(tarea,index) in tareas" :key="index">
            {{tarea}} <button @click="removeTarea(index)" class="btn btn-primary">Borrar</button>
        </div>        
    </div>
</template>
<script>
export default {
    name:"form-comp",
    data(){
        return{
            tarea:'',
            tareas:[]
        }
    },
    methods: {
        addTarea(){
            this.tareas.push(this.tarea)
            console.log(this.tareas)
        },
        removeTarea(index){
            this.tareas.splice(index,1)//TODO:No creo que esté bien
            
            console.log(this.tareas)
}
    },
}
</script>
<style >
    
</style>