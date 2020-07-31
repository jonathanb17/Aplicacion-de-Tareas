<template>
    <div>
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <h1>Aplicacion de Tareas</h1>     
                   
                         <form v-on:submit="agregarTareas">
                            <input type="text" v-model="tareasa.titulo"  class="form-control">
                            <input type="submit" value="Add" class="btn btn-block btn-primary mt-2">
                        </form>

                       <table class="table">
                            <thead>
                                <tr>
                                    <th>Hecho</th>
                                    <th>Tarea</th>
                                    <th>Eliminar</th>
                                </tr>
                            </thead>

                            <tbody>
                                    <tr v-for="(tarea,index) in tareas" v-bind:key="index" >
                                      
                                        <td>
                                            <input type="checkbox" v-model="tarea.hecho">
                                        </td>

                                        <td :class="{tareaRealizada:tarea.hecho}">
                                            {{tarea.titulo}}
                                        </td>
                                        <td>
                                            <button v-on:click="deleteTask(tarea)" class="btn btn-danger btn-block">
                                                Delete Task
                                            </button>
                                        </td>
                                    </tr>
                            </tbody>
                    </table>
                </div><!--fin div-->
                
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {     
                tareas:[
                        {
                            titulo:"tarea 1",
                            hecho : true
                        },
                        {
                            titulo:"tarea 2",
                            hecho : false
                        },
                        {
                            titulo:"tarea 3",
                            hecho : false
                        }
                    ],
                 tareasa :{},
            }
        }, // fin date
        methods:{

            deleteTask: function (tarea) {
                this.tareas.splice(this.tareas.indexOf(tarea),1);
            },
            agregarTareas: function (e) {
                e.preventDefault();
                this.tareas.push(this.tareasa); 
                this.tareasa= {}; // reinicia el input
          },

        }
} // fin export default
</script>


<style>
    .container{
        background :#ccc;
    }

    .tareaRealizada{
        text-decoration: line-through;
      }
</style>
