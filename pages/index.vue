<template>
  <div>
  <h2 style="text-align:center">Para receber nossas ofertas informe seu Nome e E-mail:</h2>
    <v-form
    ref="form"
    v-model="valid"
    lazy-validation
  >
    <v-text-field
      v-model="name"
      :counter="30"
      :rules="nameRules"
      label="Nome"
      required
    ></v-text-field>

    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
    ></v-text-field>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Enviar
    </v-btn>
  </v-form>
  </br>
    <v-container>    
      <v-carousel>
        <v-carousel-item
          v-for="(item,i) in imagens"
          :key="i"
          :src="item"
          reverse-transition="fade-transition"
          transition="fade-transition"
        ></v-carousel-item>
      </v-carousel>
    </v-container>

      <v-container>
        <v-row justify="space-around">
          <v-col
            v-for="prod in produtos"
            :key="prod"
            cols="12"
            md="4"
          >
            <v-sheet
              class="pa-12"
              color="white"
            >
              <v-sheet
                :elevation="prod.elevation"
                class="mx-auto"
                height="350"
                width="250"
                color="white"
              ><v-img
                  :lazy-src="prod.img"
                  max-height="270"
                  max-width="250"
                  :src="prod.img"
                  
                ></v-img>
                <h3 style="color:black;margin-left:10px;margin-top:15px">{{prod.title}}</h3>
                <h3 style="color:black;margin-left:10px;margin-top:10px">Por apenas {{prod.price}}</h3>
      
              </v-sheet>
            </v-sheet>
          </v-col>
        </v-row>
      </v-container>
  </div>
</template>

<script>
  export default{
    data(){
      return {
        teste: 'ABC',
        model: 0,
        imagens: [
          '/slide1.png',
          '/slide2.png',
          '/slide3.png',
          '/slide4.png',
        ],
        elevations: [0, 1, 1, 1, 1, 1],
        produtos:[{
          elevation: 1,
          img: '/furadeira.jpg',
          price: 'R$150,00',
          title:'Furadeira'
        },
        {
          elevation: 1,
          img: '/pneu.jpg',
          price: 'R$270,95',
          title:'Pneu'
        },
        {
          elevation: 1,
          img: '/caixa.jpg',
          price: 'R$99,00',
          title:'Cx. de Ferramentas'
        },
        {
          elevation: 1,
          img: '/ferro.jpg',
          price: 'R$25,00',
          title:'Ferro de Solda'
        },
        {
          elevation: 1,
          img: '/lamp.jpg',
          price: 'R$7,99',
          title:'Lâmpada de Led'
        },
        {
          elevation: 1,
          img: '/soprador.jpg',
          price: 'R$115,00',
          title:'Soprador Térmico'
        }],
        valid: true,
      name: '',
      nameRules: [
        v => !!v || 'Nome é obrigatório',
        v => (v && v.length <= 30) || 'Nome deve conter menos de 30 caracteres',
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail é obrigatório',
        v => /.+@.+\..+/.test(v) || 'E-mail inválido',
      ]
      }
    },
      methods: {
      validate () {
        this.$refs.form.validate()
      },
    },
  }  
</script>

<style>
</style>