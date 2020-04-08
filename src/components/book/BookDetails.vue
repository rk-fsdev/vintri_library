<template>
  <div class="book-details">
    <Information name="Title" :content="title" />
    <Information name="Copyright Date" :content="copyrightDate" />
    <Information name="Edition" :content="edition" />
    <Information name="Date Published" :content="datePublished" />
    <Information name="Excerpt" :content="excerpt" />
  </div>
</template>
<script>
import Information from "@/components/Information";

export default {
  name: "BookDetails",
  components: { Information },
  props: {
    title: String,
    copyrightDate: Number,
    datePublished: String,
    edition: Number,
    excerpt: String,
    overview: String
  }
};
</script>
<style lang="scss" scoped></style>
