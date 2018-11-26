<template>
  <div>
    <h1>{{ title }}</h1>
    <ul>
      <book-item v-for="book in books" :book="book" :key="book.title"/>
    </ul>
    <book-form @addBook="appendBook"/>
  </div>
</template>

<script>
  import BookForm from './BookForm';
  import BookItem from './BookItem';

  export default {
    name: 'BookList',
    components: { BookForm, BookItem },
    data: function () {
      return {
        title: 'All Books',
        books: [
          { title: 'Self-Reliance', author: 'Ralph Waldo Emerson' },
          { title: 'American Gods', author: 'Neil Gaiman' },
          { title: 'Amusing Ourselves to Death', author: 'Neil Postman' },
        ],
      };
    },
    methods: {
      appendBook: function (bookTitle, bookAuthor) {
        this.books.push({ title: bookTitle, author: bookAuthor });
      },
    },
  };
</script>

<style scoped>
  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }
</style>
