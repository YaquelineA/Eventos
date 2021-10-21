<template>
    <div>
        {{Titulo}}
    </div>
</template>

<script>
export default {
    mame: 'ColumnTable',
    props : {
        Hora : String,
        Sesiones : Array, 
    },
    data(){
        return{
            Titulo: ''
        }
    },
    mounted(){
        this.ValidarSesion();
    },
    methods :{
        ValidarSesion(){
            this.Sesiones.forEach(Sesion => {
                let HoraSesion = Sesion.start.substr(11,2); 

                if(HoraSesion == this.Hora){
                    this.Titulo = Sesion.title;
                }     
            });
        }
    }
}
</script> 