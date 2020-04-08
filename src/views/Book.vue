<template>
  <div v-if="bookDetails" class="book">
    <h1 class="text-center">Book Details</h1>
    <v-tabs v-model="tab">
      <v-tab
        v-for="({ text, value }, index) in tabs"
        :key="index"
        :href="`#${value}`"
      >
        {{ text }}
      </v-tab>
      <v-tab-item value="book-details">
        <BookDetails
          :title="bookDetails.title"
          :copyrightDate="bookDetails.copyright_date"
          :datePublished="bookDetails.date_published"
          :edition="bookDetails.edition"
          :excerpt="bookDetails.excerpt"
          :overview="bookDetails.overview"
        ></BookDetails>
      </v-tab-item>
      <v-tab-item value="collect-information">
        <CollectInformation :reviews="bookDetails.reviews"></CollectInformation>
      </v-tab-item>
      <v-tab-item value="library-details">
        <LibraryDetails
          :loanHistory="bookDetails.loan_history"
        ></LibraryDetails>
      </v-tab-item>
    </v-tabs>
  </div>
</template>
<script>
import { bookList } from "@/services/dummyData";
import {
  BookDetails,
  CollectInformation,
  LibraryDetails
} from "@/components/book";

export default {
  name: "Book",
  components: {
    BookDetails,
    CollectInformation,
    LibraryDetails
  },
  data: function() {
    return {
      bookDetails: null,
      isbn: this.$route.params.isbn,
      tabs: [
        { text: "Book Details", value: "book-details" },
        { text: "Collect Information", value: "collect-information" },
        { text: "Library Details", value: "library-details" }
      ],
      tab: ""
    };
  },
  mounted() {
    this.bookDetails = bookList.filter(
      book => book.isbn === parseInt(this.isbn)
    )[0];

    if (!this.bookDetails) {
      this.$router.push("/");
    }
  }
};
</script>
<style lang="scss" scoped>
.book {
  padding: 100px;
}
</style>
