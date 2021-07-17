<template>
  <v-container>
    <v-row justify="space-around">
      <v-col
        v-for="elevation in elevations"
        :key="elevation"
        cols="12"
        md="4"
      >
        <v-sheet
          class="pa-12"
          color="white"
        >
          <v-sheet
            :elevation="elevation"
            class="mx-auto"
            height="350"
            width="275"
            color="white"
          ></v-sheet>
        </v-sheet>
      </v-col>
    </v-row>
  </v-container>
</template>


<script>
  export default {
    data: () => ({
      elevations: [0, 1, 1, 1, 1, 1],
    }),
  }
</script>