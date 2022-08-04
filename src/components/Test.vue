<template lang="es">
    <div class="content">
        <h3> Calculadora de Potencia</h3>
        <label> Corriente</label>
         <input class="inputs" type="number" v-model="corriente">
         <br>
         
        <label> Voltaje</label>
         <input class="inputs" type="number" v-model="voltaje">
         <br>
        <label> Resistencia</label>
        <input class="inputs" type="number" v-model="resistencia">
          <br>
                <br>
        <button class="button" @click="calculatePower()">Calcular</button>
        <br>
        <br>
        <label>La potencia es: {{potencia}} </label>
    </div>
</template>

<script>


    export default{

        data(){
            return {
            corriente:0,
            potencia:0,
            voltaje:0,
            resistencia:0
            }
        }
        
        ,

          methods:{
            calculatePower(){
               if(this.resistencia==0) {
                                this.potencia= this.corriente * this.voltaje
                                console.log(this.potencia)
               }
                else if(this.corriente==0){
                    this.potencia= (this.voltaje* this.voltaje)/(this.resistencia)
                }
                else if(this.voltaje==0){
                    this.potencia= (this.corriente* this.corriente)* this.resistencia
                }
                else{
                    alert("Solo utilizar dos medidas")
                }
                return this.potencia
        }
    }
    }
			
  

</script>
<style>
    .inputs{
        margin: 10px;  
        text-align: center;
    }
    .content{
       display: flex; 
       justify-content: center;
       flex-flow: column;
        
    }
    .button {
  background-color: #4CAF50; /* Green */
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  border-radius: 20px;
}
</style>