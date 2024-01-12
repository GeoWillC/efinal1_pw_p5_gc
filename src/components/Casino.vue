<template>
    <div id="container">
        <img v-bind:src="imagen" alt="Uno">
    <br>
    <label> XXXXXXXXX </label>
    </div>
</template>


<script>

const inicial = 
["https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
"https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/2.svg",
"https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/3.svg"]

export default {
    props:{
        valor:{
            type:Number,
            default:0
        },
        validacion:{
            type:Boolean,
            default:false,
            validator(value){
                if(value!==false){
                   
                }
            }
        }
    },
    data() {
        return{
            imagen:inicial[this.valor],
            respuesta:null,
            validator:this.validacion
        }
    },
    methods: {
        async consumidorAPI() {
            const {answer,image} = await fetch("https://yesno.wtf/api").then(r => r.json());
            console.log(answer);
            this.imagen=image;
            this.respuesta=answer;
        },
        consumir(){
           this.consumidorAPI()
           this.valor=false
        },
        consola(){
            console.log("Alo")
        }
       
    },
    watch: {

    }

}
</script>

<style scoped>


img{
    width: 220px;
    height: 150px;
    border: solid 5px; 
}

</style>