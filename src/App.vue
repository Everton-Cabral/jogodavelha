<template>
  <div id="app">
    
    <div v-show="resultado" class="card">
      <h1>  O Jogador {{jogada%2 > 0 ? '1°' : '2°'}} Venceu!</h1>

      <button id="novoJogo" @click="novoJogo">Novo Jogo?</button>
      
    </div>  

    <div class="app" :style="ativador">
      
      <div class="menu">

        <tamplate class="escolha" v-if="jogador1 === ''">

          <h2> O Primeiro Jogador deve escolher entre:</h2>
            <span>
              <img src="./assets/img/circulo.png" class="img-menu" alt="circulo" 
              @click="escolha('circulo')">
              
              <img src="./assets/img/x.png" class="img-menu" alt="x"
              @click="escolha('x')">
            </span>
      
        </tamplate>

        <div class="escolha" v-else>

          <h2> Vez do jogador {{jogada%2 == 0 ? 1 : 2}}°</h2>

        </div>

      </div>
  
        <div class="container">
          
            <div class="traco"  :class="classe"></div>
        
          <div class="bloco" id="b1" @click="jogada++; 
            inserindo() ? figuras.b1 = jogador1 : figuras.b1 = jogador2" >

              <div v-if="figuras.b1 === 'circulo'">
                  <img src="./assets/img/circulo.png" alt="Circulo" class="figura">
              </div>

              <div v-if="figuras.b1 === 'x'">
                  <img src="./assets/img/x.png" alt="x" class="figura">
              </div>

          </div>

          <div class="bloco" id="b2" @click=" jogada++; 
            inserindo() ? figuras.b2 = jogador1 : figuras.b2 = jogador2">
                <div v-if="figuras.b2 === 'circulo'">
                    <img src="./assets/img/circulo.png" alt="Circulo" class="figura">
                </div>

                <div v-if="figuras.b2 === 'x'">
                    <img src="./assets/img/x.png" alt="x" class="figura">
                </div>
          </div>

          <div class="bloco" id="b3" @click="jogada++; 
            inserindo() ? figuras.b3 = jogador1 : figuras.b3 = jogador2">
                <div v-if="figuras.b3 === 'circulo'">
                    <img src="./assets/img/circulo.png" alt="Circulo" class="figura">
                </div>

                <div v-if="figuras.b3 === 'x'">
                  <img src="./assets/img/x.png" alt="x" class="figura">
                </div>
          </div>

          <div class="bloco" id="b4" @click="jogada++; 
            inserindo() ? figuras.b4 = jogador1 : figuras.b4 = jogador2">
                <div v-if="figuras.b4 === 'circulo'">
                    <img src="./assets/img/circulo.png" alt="Circulo" class="figura">
                </div>

                <div v-if="figuras.b4 === 'x'">
                    <img src="./assets/img/x.png" alt="x" class="figura">
                </div>
          </div>

          <div class="bloco" id="b5" @click="jogada++; 
            inserindo() ? figuras.b5 = jogador1 : figuras.b5 = jogador2">
                <div v-if="figuras.b5 === 'circulo'">
                    <img src="./assets/img/circulo.png" alt="Circulo" class="figura">
                </div>

                <div v-if="figuras.b5 === 'x'">
                    <img src="./assets/img/x.png" alt="x" class="figura">
                </div>
          </div>

          <div class="bloco" id="b6" @click="jogada++; 
            inserindo() ? figuras.b6 = jogador1 : figuras.b6 = jogador2">
              <div v-if="figuras.b6 === 'circulo'">
                  <img src="./assets/img/circulo.png" alt="Circulo" class="figura">
              </div>

              <div v-if="figuras.b6 === 'x'">
                  <img src="./assets/img/x.png" alt="x" class="figura">
              </div>
          </div>

          <div class="bloco" id="b7" @click="jogada++; 
            inserindo() ? figuras.b7 = jogador1 : figuras.b7 = jogador2">
              <div v-if="figuras.b7 === 'circulo'">
                  <img src="./assets/img/circulo.png" alt="Circulo" class="figura">
              </div>

              <div v-if="figuras.b7 === 'x'">
                  <img src="./assets/img/x.png" alt="x" class="figura">
              </div>
          </div>

          <div class="bloco" id="b8" @click="jogada++; 
            inserindo() ? figuras.b8 = jogador1 : figuras.b8 = jogador2">
              <div v-if="figuras.b8 === 'circulo'">
                  <img src="./assets/img/circulo.png" alt="Circulo" class="figura">
              </div>

              <div v-if="figuras.b8 === 'x'">
                  <img src="./assets/img/x.png" alt="x" class="figura">
              </div>
          </div>

          <div class="bloco" id="b9" @click="jogada++; 
            inserindo() ? figuras.b9 = jogador1 : figuras.b9 = jogador2">
              <div v-if="figuras.b9 === 'circulo'">
                  <img src="./assets/img/circulo.png" alt="Circulo" class="figura">
              </div>

              <div v-if="figuras.b9 === 'x'">
                <img src="./assets/img/x.png" alt="x" class="figura">
              </div>
          </div>

        </div>
    </div>

      

  </div>
 

</template>


<script>



export default {
  
  
  data(){
    return{
      jogador1: '',
      jogador2: '',
      jogada: 0,
      figuras: {b1:'b1', b2:'b2',b3:'b3',b4:'b4',b5:'b5',b6:'b6',b7:'b7',b8:'b8',b9:'b9'},
      classe:'',
      ativador: '',
      resultado: false,
    }
  },
  methods:{

    escolha(params){
      if(params == 'circulo'){
          this.jogador1 = 'circulo'
          this.jogador2 = 'x'
      } else{
          this.jogador1 = 'x'
          this.jogador2 = 'circulo'
      }
    },

    inserindo(){
       if(this.jogada%2 > 0){
          return true 
      }else{
        return false
      } 
    },

    batida(a,b,c){
      if(a == b && a == c){
        return true
      } else {
        return false
      }
    },

   batidaClasse(params){
    this.classe = params
    this.ativador = 'opacity: 0.3;'
    setTimeout(() => { this.resultado = true}, "1000")
   },

   novoJogo(){
    this.figuras = {b1:'b1', b2:'b2',b3:'b3',b4:'b4',b5:'b5',b6:'b6',b7:'b7',b8:'b8',b9:'b9'}
    this.jogada = 0
    this.classe = ''
    this.ativador = ''
    this.resultado = false
    this.jogador1 = ''
    this.jogador2 = ''
   }
   
  },
  
  watch:{
    figuras:{
      handler(){
        if(this.batida(this.figuras.b2,this.figuras.b5,this.figuras.b8) ){
          
          this.batidaClasse('batidaColuna2')
          
        } else if(this.batida(this.figuras.b1,this.figuras.b4,this.figuras.b7) ){

            this.batidaClasse('batidaColuna1')

        } else if(this.batida(this.figuras.b1, this.figuras.b5, this.figuras.b9) ){
          
            this.batidaClasse('batidaDiagonal1')

        } else if(this.batida(this.figuras.b3, this.figuras.b5, this.figuras.b7) ){

            this.batidaClasse('batidaDiagonal2')
            
        } else if(this.batida(this.figuras.b3, this.figuras.b6, this.figuras.b9) ){

            this.batidaClasse('batidaColuna3')

        } else if(this.batida(this.figuras.b1,this.figuras.b2,this.figuras.b3) ){

           this.batidaClasse('batidaLinha1')

        } else if(this.batida(this.figuras.b4, this.figuras.b5, this.figuras.b6) ){

           this.batidaClasse('batidaLinha2')
        
        } else if(this.batida(this.figuras.b7, this.figuras.b8, this.figuras.b9)){

           this.batidaClasse('batidaLinha3')

        }
      },
      deep: true
    }
  }
  
}
</script>

<style>
  @import './style.css';

</style>
