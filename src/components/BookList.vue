<template>
  <div>
    <book-form @addBook='appendBook'/>
    <h1>{{ title }}</h1>
    <ul>
      <book-item v-for="book in books" :key="book.isbn" :book="book">
      </book-item>
    </ul>
  </div>
</template>

<script>
import BookItem from './BookItem';
import BookForm from './BookForm';

export default {
  name: "BookList",
  components: {
    BookItem,
    BookForm,
  },
  methods:{
      appendBook(bookTitle, bookAuthor){
          this.books.push( { title: bookTitle, author: bookAuthor});
      },
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