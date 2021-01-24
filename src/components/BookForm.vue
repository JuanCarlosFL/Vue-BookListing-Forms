<template>
  <form class="" action="#" method="post" v-on:submit.prevent="bookSubmit(bookData)">
    <input type="text" name="title" value="" placeholder="Book Title" v-model="bookData.bookTitle">
    <input type="text" name="author" value="" placeholder="Book Author" v-model="bookData.bookAuthor">
    <div>
      <label for="finishedReading">Finished Reading</label>
      <input v-model="bookData.finishedReading" type="checkbox" id="finishedReading" />
    </div>
    <div>
      <label for="borrowed">borrowed</label>
      <input type="radio" value="borrowed" v-model="bookData.ownership" id="borrowed">
      <label for="bought">bought</label>
      <input type="radio" value="bought" v-model="bookData.ownership" id="bought">
    </div>
    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ['books'],
  data() {
    return {
      bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: false,
        ownership: []
      }
    }
  },
  methods: {
    bookSubmit(bookData){
      this.$emit('addBook', bookData);
    }
  }
}
</script>

<style scoped>

</style>
