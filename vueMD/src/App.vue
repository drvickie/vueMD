<script setup></script>

<template>
  <div class="editor-container">
    <h1 class="app-title">Markdown Editor</h1>

    <div class="panes">
      <div class="pane input-pane">
        <h2>Input</h2>
        <textarea v-model="markdown" />
      </div>

      <div class="pane output-pane">
        <h2>Output</h2>
        <div class="preview">
          <Markdown :source="markdown" :options="markdownOptions" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import Markdown from "vue3-markdown-it";

const markdown = ref<string>(
  "# Hello Markdown\n\nType **bold**, *italic*, or `code` here."
);

const markdownOptions = {
  html: false,
  linkify: true,
  typographer: true,
};
</script>

<style scoped>
* {
  box-sizing: border-box;
  font-family: Arial, sans-serif;
}

.editor-container {
  padding: 20px;
  max-width: 1000px;
  margin: 0 auto;
}

.app-title {
  font-size: 2rem;
  font-weight: bold;
  text-align: center;
  margin-bottom: 20px;
}

.panes {
  display: flex;
  gap: 20px;
}

.pane {
  flex: 1;
  border: 2px solid #ccc;
  border-radius: 6px;
  padding: 10px;
}

.pane h2 {
  margin-top: 0;
  font-size: 1.2rem;
  border-bottom: 1px solid #ddd;
  padding-bottom: 5px;
}

textarea {
  width: 100%;
  height: 300px;
  border: none;
  outline: none;
  resize: none;
  font-size: 1rem;
}

.preview {
  min-height: 300px;
}

.preview h1 {
  font-weight: bold;
  font-size: 2rem;
  margin: 10px 0;
}

.preview code {
  background: #f4f4f4;
  padding: 2px 4px;
  border-radius: 4px;
  font-family: monospace;
}
</style>



