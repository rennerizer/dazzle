<template>
  <div id="notebook">
    
    <div class="container">
      <div class="row">

        <div class="col-sm-4">
          <!-- Main Pain -->
          <section class="main">
            <textarea v-model="content"></textarea>
          </section>
        </div>

        <div class="col-sm-8">
          <!-- Preview Pane -->
          <aside class="preview" v-html="notePreview">

          </aside>
        </div>

      </div>
    </div>

  </div>
</template>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>

<script>

export default {
  data () {
    return {
      content: 'This is a note.'
    }
  },
  computed: {
    notePreview () {
      return marked(this.content);
    }
  }
};

</script>
