<template>
  <div class="home">
    <div id="editor">
      <textarea v-model="input"></textarea>
    </div>
    <div id="preview">
      <div v-html="compiledMarkdown"></div>
    </div>
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
  height: 100%;
  width: 50%;
  vertical-align: top;
  box-sizing: border-box;
  overflow-y: scroll;
  overflow-x: hidden;
}

#editor textarea {
  font-family: 'Monaco', courier, monospace;
  font-size: 14px;
  border: none;
  padding: 20px;
  outline: none;
  height: 100%;
  width: 100%;
}

#preview {
  padding: 0 20px;
  background-color: #f7f7f7;
}

#preview div {
  height: 100%;
}

#preview img {
  max-width: 100%;
  display: block;
}
</style>