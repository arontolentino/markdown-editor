<template>
  <div id="app">
    <section id="title">
      <h1>Markdown Editor</h1>
    </section>

    <section id="header">
      <div>
        <h2>Markdown</h2>
      </div>
      <div id="header-preview">
        <h2>Preview</h2>
      </div>
    </section>

    <section id="editor">
      <div id="input">
        <textarea v-model="input"></textarea>
      </div>
      <div id="preview">
        <div v-html="compiledMarkdown"></div>
      </div>
    </section>
  </div>
</template>

<script>
import marked from 'marked';

export default {
  data: function() {
    return {
      input:
        'Heading\n=======\n\nSub-heading\n-----------\n \n### Another deeper heading\n \nParagraphs are separated\nby a blank line.\n\nLeave 2 spaces at the end of a line to do a  \nline break\n\nText attributes *italic*, **bold**, \n`monospace`, ~~strikethrough~~ .\n\nShopping list:\n\n  * apples\n  * oranges\n  * pears\n\nNumbered list:\n\n  1. apples\n  2. oranges\n  3. pears\n\nThe rain---not the reign---in\nSpain.\n\n Heading\n=======\n\nSub-heading\n-----------\n \n### Another deeper heading\n \nParagraphs are separated\nby a blank line.\n\nLeave 2 spaces at the end of a line to do a  \nline break\n\nText attributes *italic*, **bold**, \n`monospace`, ~~strikethrough~~ .\n\nShopping list:\n\n  * apples\n  * oranges\n  * pears\n\nNumbered list:\n\n  1. apples\n  2. oranges\n  3. pears\n\nThe rain---not the reign---in\nSpain.\n\n '
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
#title {
  background-color: #23cb84;
  height: 70px;
  display: flex;
  justify-content: center; /* align horizontal */
  align-items: center;
}

#title h1 {
  text-align: center;
  font-weight: 300;
  font-size: 20px;
  margin: 0;
  color: white;
}

#header #header-preview {
  background-color: #f7f7f7;
}

#header {
  display: flex;
}

#header div {
  width: 50%;
  border-bottom: 1px solid #cecece;
}

#header h2 {
  font-size: 14px;
  font-weight: 300;
  padding-left: 20px;
}

* {
  box-sizing: border-box;
}

html {
  margin: 0;
  overflow: hidden;
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}

#app {
  height: 100vh;
  width: 100%;
  font-family: 'Roboto', sans-serif;
}

#editor {
  display: flex;
  width: 100%;
}

#input,
#preview {
  height: calc(100vh - 132px);
  width: 50%;
  vertical-align: top;
  overflow-y: scroll;
  overflow-x: hidden;
}

#input textarea {
  font-family: 'Monaco', courier, monospace;
  font-size: 14px;
  height: 100%;
  border: none;
  padding: 20px;
  outline: none;
  box-sizing: border-box;
  resize: none;
  width: 100%;
}

#preview {
  padding: 0 20px;
  background-color: #f7f7f7;
}

#preview img {
  max-width: 100%;
  display: block;
}
</style>