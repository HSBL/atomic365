<template>
  <div class="calculator">
    <h1>Hello Calculator</h1>
    <v-row>
      <v-col cols="12">
        <v-text-field
          label="Insert current"
          :rules="rules"
          hide-details="auto"
        ></v-text-field>
      </v-col>
    </v-row>
  </div>
</template>

<script>
  export default {
    data: () => ({
      rules: [
        value => !!value || 'Required.',
      ],
    }),
  }
</script>

<style>
</style>