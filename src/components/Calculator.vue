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
        <div class="result">
        <p>by the end of the year :</p>
        <h1>{{ result }}</h1>
        </div>
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
      if (Number(this.initial)) {
        var init = Number(this.initial);
        for (let i = 0; i < 365; i++) {
          init += init * 0.01;
        }
        return init;
      } else {
        return "calculating...";
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.result {
    padding: 2rem;

    p {
        font-size: larger;
    }
}
</style>