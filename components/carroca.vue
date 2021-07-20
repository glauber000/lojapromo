<template>
    <v-container>    
      <v-carousel>
        <v-carousel-item
          v-for="(item,i) in img"
          :key="i"
          :src="item"
          reverse-transition="fade-transition"
          transition="fade-transition"
        ></v-carousel-item>
      </v-carousel>
    </v-container>
</template>


<script>

export default ({
    data() {
        return{
            titulo:'ABC'
        }
        
    },
    props:{
        img:[]
    }
})
</script>
