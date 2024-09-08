<template>
    <h1>{{msg}}</h1>
    <form v-on:submit.prevent="mostrarDatos">
        <label for="">Nombre:  <input type="text" v-model="nombreIngresado"></label>
        <label for="">Apellido:<input type="text" v-model="apellidoIngresado"></label>
        <label for="">Correo:<input type="mail" v-model="mailIngresado"></label>
        <label for="">Edad:<input type="number" min="1" max="99" v-model="edadIngresada"></label>
        <input type="submit"> 
    </form>
    <!-- <input type="text" v-model="nombreIngresado"> 
    <input type="text" :value="nombreIngresado"> -->
    <hr>
    <h2>Recuerda esto:</h2>
    <p>Tu nombre es: {{ nombreMostrado }} {{ apellidoMostrado }} y tienes {{ edadMostrada }} años</p>
    <p>lo que significa que estas en la siguiente etapa:</p>
    <p v-if="edadMostrada < 14" class="etapa">Niñez</p>   
    <p v-else-if="edadMostrada < 18" class="etapa">Adolescencia</p>   
    <p v-else-if="edadMostrada < 36" class="etapa">Adulto Joven</p>   
    <p v-else-if="edadMostrada < 65" class="etapa">Adulto</p>   
    <p v-else class="etapa">Tercera Edad</p>   
    <!-- <p>{{ nombreIngresado }}</p> -->
</template>

<script>
export default{
    name: 'SessionDosForm',
    props:{
        msg: String
    },
    data(){
        return{
            nombreIngresado:' ',
            nombreMostrado:'',
            apellidoIngresado:'',
            apellidoMostrado:'',
            mailIngresado:'',
            mailMostrado:'',
            edadIngresada:0,
            edadMostrada: 0,
            prueba:'',
        }
    },

    methods: {
        mostrarDatos(){
            this.nombreMostrado = this.nombreIngresado;
            this.apellidoMostrado = this.apellidoIngresado;
            this.mailMostrado = this.mailIngresado;
            this.edadMostrada = this.edadIngresada;
           alert(`Saludos ${ this.nombreMostrado } ${ this.apellidoMostrado }, tu correo es ${ this.mailMostrado }`);  
            this.nombreIngresado='';
            this.apellidoIngresado='';
            this.mailIngresado='';
            this.edadIngresada='';
        }
    }
}
</script>

<style>
    .etapa{
        font-size: 20px;
    }
</style>