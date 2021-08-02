<template>
  <v-footer dark padless app inset>
    <v-card class="flex" flat tile color="green" :elevation="10">
      <v-text class="py-2 white--text text-center">
        {{ new Date().getFullYear() }} - <strong>Ezee Technologies Ltd</strong>
      </v-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {};
</script>

<style scoped></style>
