<template lang="es">
    <div class="content">
        <h3> Calculadora de Potencia</h3>
        <label> Corriente</label>
        <div>
          <input class="inputs" type="number" v-model="corriente"> <span>A</span>
        </div>
         <br>
         
        <label> Voltaje</label>
         <div>
                        <input class="inputs" type="number" v-model="voltaje"> <span>V</span>
         </div>                                    
         <br>
        <label> Resistencia</label>
        <div>
            <input class="inputs" type="number" v-model="resistencia"> <span>Ω</span>
        </div>
          <br>
                 <br>
        <button class="button" @click="calculatePower()">Calcular</button>
        <br>
        <br>
        <label>La potencia es: {{potencia}} W</label>
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
        width:100px;
        text-align: center;
        outline: 0;
        border-width: 0 0 2px;
    }
    .content{
       display: flex; 
       justify-content: center;
       align-items: center;
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