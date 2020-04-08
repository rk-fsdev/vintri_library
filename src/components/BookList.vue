<template>
  <v-card class="book">
    <v-card-title>
      Book List
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
      :items="lists"
      :search="search"
      :itmes-per-page="10"
      @click:row="openDetails"
      class="book_table"
    ></v-data-table>
  </v-card>
</template>
<script>
export default {
  name: "BookList",
  props: {
    lists: Array
  },
  data: function() {
    return {
      search: "",
      headers: [
        { text: "Title", value: "title" },
        { text: "Authors", value: "authors" },
        { text: "Edition", value: "edition" },
        { text: "Date Published", value: "date_published" },
        { text: "Due Date", value: "due_date" }
      ]
    };
  },
  methods: {
    openDetails({ isbn }) {
      this.$router.push(`/book/${isbn}`);
    }
  }
};
</script>
<style lang="scss" scoped></style>
