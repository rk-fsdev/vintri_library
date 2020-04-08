<template>
  <v-card>
    <v-card-title>
      Check Out Records
      <v-spacer></v-spacer>
      <v-text-field
        v-model="search"
        append-icon="mdi-magnify"
        label="Search"
        single-line
        hide-details
      ></v-text-field>
    </v-card-title>
    <v-data-table
      :headers="headers"
      :items="records"
      :search="search"
    ></v-data-table>
  </v-card>
</template>
<script>
export default {
  name: "CheckOut",
  props: {
    records: Array
  },
  data: function() {
    return {
      search: "",
      headers: [
        { text: "By", value: "check_out_by" },
        { text: "Date", value: "check_out_date" },
        { text: "Location", value: "check_out_location" },
        { text: "Condition", value: "check_out_condition" }
      ]
    };
  }
};
</script>
<style lang="scss" scoped></style>
