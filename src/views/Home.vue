<template>
  <div class="home">
    <h1 class="home_title">Library</h1>
    <BookList :lists="bookList" />
  </div>
</template>

<script>
// @ is an alias to /src
import BookList from "@/components/BookList.vue";

import { bookList } from "@/services/dummyData";

export default {
  name: "Home",
  components: {
    BookList
  },
  data: function() {
    return {
      bookList
    };
  }
};
</script>
<style lang="scss" scoped>
.home {
  padding: 100px;
  &_title {
    text-align: center;
  }
}
</style>
