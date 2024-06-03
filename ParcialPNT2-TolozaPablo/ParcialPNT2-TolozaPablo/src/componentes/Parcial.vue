<template>

  <section class="src-componentes-ingreso">
    <div class="jumbotron">
      <h2>Ingreso Texto</h2>
      <hr>
      <br>

      <form >
        
        <!-- Campo nombre -->
        <div class="form-group">
          <label for="texto">texto</label>
          <input 
            id="texto" 
            type="text" 
            class="form-control" 
            v-model.trim="formData.texto"
            
          >
          
        </div>

        
      </form>

      <br>
      <hr>

      <!-- Representacion del texto -->
      <h2>Texto Modificado</h2>
      <br>
      <p>Cantidad Caracteres {{ contarCaracteres }}</p>
      <p>1) Cambiar Vocales -> {{ cambiarVocales() }}</p>
      <p>2) Texto en Mayusculas -> {{ mostrarEnMayusculas() }}</p>
      <p>3) Texto en Minusculas -> {{ mostrarEnMinusculas() }}</p>
      <p>4) Alternar Mayusculas 1 -> {{ alternarMayusculas1() }}</p>
      <p>5) Alternar Mayusculas 2 -> {{ alternarMayusculas2() }}</p>
      <br>
      <p>Respuestas Cuestionario : <br>
        1->C <br> 2->C <br> 3->A </p>
    

    </div>
  </section>

</template>

<script>

  export default  {
    name: 'src-componentes-ingreso',
    props: [],
    mounted () {

    },

    data () {
      return {
        formData : this.getInitialData(),
      }
    },

    methods: {
      getInitialData() {
        return {
          texto : ""
        }
      },
      mostrarEnMayusculas(){
        return this.formData.texto.toUpperCase()
      },
      mostrarEnMinusculas(){
        return this.formData.texto.toLowerCase()
      },
      alternarMayusculas1(){
        let textoModificado=""
        let textoArray = this.formData.texto.split("")
        let i=0
        for(const elemento of textoArray){
          if(i%2 === 0){
            textoModificado += elemento.toUpperCase()
          }
          else {
            textoModificado += elemento.toLowerCase()
          }
          i++

        }
        return textoModificado
      },
      alternarMayusculas2(){
        let textoModificado=""
        let textoArray = this.formData.texto.split("")
        let i=0
        for(const elemento of textoArray){
          if(i%2 === 0){
            textoModificado += elemento.toLowerCase()
          }
          else {
            textoModificado += elemento.toUpperCase()
          }
          i++

        }
        return textoModificado
      },
      cambiarVocales(){
        let textoOriginal=this.formData.texto.toLowerCase()
        let textoModificado = ""
        
        for(const caract of textoOriginal){
          switch (caract) {
            case "a":
              textoModificado += "u"
              
              break
            case "e":
              textoModificado+= "o"
              break 
            case "o":
              textoModificado+= "e"
              break   
            case "u":
              textoModificado+= "a"
              break 
            default:
              textoModificado += caract;
          }

        }
        return textoModificado
      }
    },

    computed: {
      contarCaracteres(){
        
        return this.formData.texto ? this.formData.texto.length : 0   
      }
    }
}


</script>

<style scoped lang="css">
  .jumbotron {
    background-color: white;
    color: rgb(106, 42, 165);
  }

  hr {
    background-color: #eee;
  }

  label {
      text-transform: capitalize;
  }
</style>
