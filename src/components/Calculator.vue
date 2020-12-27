<template>
  <div class="calculator">
    <h1>Hello Calculator</h1>
    <v-row>
      <v-col cols="12">
        <v-text-field
          label="Insert current"
          v-model="initial"
          :rules="rules"
          hide-details="auto"
        ></v-text-field>

        <h1>by the end of on year : {{ result }}</h1>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data: () => ({
    rules: [
      (value) => !!value || "Required.",
      (value) => Number(value) || "Must be a Number",
    ],
    initial: null,
  }),
  computed: {
    result: function () {
      return Number(this.initial) + 5;
    },
  },
};
</script>

<style>
</style>