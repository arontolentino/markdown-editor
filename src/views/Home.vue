<template>
  <div class="home">
    <textarea id="editor" v-model="input"></textarea>
    <div id="preview">
      <div v-html="compiledMarkdown"></div>
    </div>
  </div>
</template>

<script>
import marked from 'marked';

export default {
  name: 'home',
  data: function() {
    return {
      input: '# hello'
    };
  },
  computed: {
    compiledMarkdown: function() {
      return marked(this.input);
    }
  }
};
</script>

<style>
html,
body,
.home {
  margin: 0;
  height: 100vh;
  width: 100%;
  font-family: 'Roboto', sans-serif;
  display: flex;
}

#editor,
#preview {
  width: 50%;
  vertical-align: top;
  box-sizing: border-box;
}

#editor {
  border: none;
  font-size: 14px;
  outline: none;
  font-family: 'Monaco', courier, monospace;
  padding: 20px;
}

#preview {
  padding: 0 20px;
  background-color: #f7f7f7;
  overflow-y: scroll;
}

#preview div {
  height: 100%;
  width: 100%;
}

#preview img {
  max-width: 100%;
  display: block;
}
</style>