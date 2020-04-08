<template>
  <v-card>
    <v-card-title>
      Check In Records
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
  name: "CheckIn",
  props: {
    records: Array
  },
  data: function() {
    return {
      search: "",
      headers: [
        { text: "Date", value: "check_in_date" },
        { text: "Location", value: "check_in_location" },
        { text: "Condition", value: "check_in_condition" },
        { text: "Librarian Id", value: "check_in_librarian_id" }
      ]
    };
  }
};
</script>
<style lang="scss" scoped></style>
