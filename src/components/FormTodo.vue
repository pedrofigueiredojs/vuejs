<template>
  <div class="form-todo form-group">
    <p>
      <input type="text" placeholder="nome" name="author" class="form-control" v-model="name" />
    </p>
    <p>
      <input type="text" placeholder="Comentário" name="message" class="form-control" v-model="message" />
    </p>
    <button v-on:click="addComment" type="submit" class="btn btn-primary">Comentar</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      message: ""
    }
  },
  methods: {
    addComment() {
      if (this.message.trim() === "") {
        return;
      }

      this.$emit('add-todo', {
        name: this.name,
        message: this.message
      })

      this.name = "";
      this.message = "";
    }
  }
}
</script>