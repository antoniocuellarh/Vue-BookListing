<template>
  <div>
    <h1>{{ title }}</h1>
    <ul>
      <book-item>
      </book-item>
    </ul>
  </div>
</template>

<script>
import BookItem from './BookItem';
export default {
  name: "BookList",
  components: {
    BookItem,
  },
  data() {
    return {
      title: "All Books",
      books: [
        { isbn: 1, title: "Self-Reliance", author: "Ralph Waldo Emerson" },
        { isbn: 2, title: "American Gods", author: "Neil Gaiman" },
        {isbn: 3,
          title: "Amusing Ourselves to Death",
          author: "Neil Postman",
        },
      ],
    };
  },
};
</script>

<style scoped>
h1,h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: block;
  margin: 0 10px;
}
</style>