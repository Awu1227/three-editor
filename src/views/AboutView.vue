<template>
    <div class="common-layout">
    <el-container>
      <el-header class="header">Header</el-header>
      <el-container>
        <el-aside class="codeSide">
          <div class="code">

          </div>
        </el-aside>
        <el-main>


        </el-main>
      </el-container>
    </el-container>
  </div>
  <!-- <div class="about">
    <RouterLink to="/">close</RouterLink>
    <RouterLink to="/about">delete</RouterLink>
  </div> -->
</template>

<script lang="ts" setup>
import * as monaco from "monaco-editor";
import { onMounted } from "vue";

const INITIAL_CODE = `
/*
This is your new 1DIV!

You have a single element to style:
<div class="a"></div>
So get creative with CSS!

You can't style the body or html elements. If you
want to change the background color, use the color
picker button in the bottom-right corner.

Useful tips:
- Use % units so your demo works in any container size.
- The 1DIV is set up in a way where 1em is always 1% of the width.
- Use multiple background-images to draw shapes.
- Use ::before/::after pseudo-elements.
- Use multiple box-shadows to duplicate shapes.
- The background color you chose is also available with var(--bg-color).
*/

.a {
  --color: gold;
  width: 50%;
  aspect-ratio: 1;
  border-radius: 50%;
  background: var(--color);
  box-shadow:
    inset 0 0 0 10em var(--color),
    inset 0 0 0 20em var(--bg-color),
    inset 0 0 0 30em var(--color),
    inset 0 0 0 40em var(--bg-color);
}`;
onMounted(() => {
  console.log(document.querySelector('.code'));
  const ditor = monaco.editor.create(document.querySelector('.code')!, {
    theme: 'vs-dark',
    model: monaco.editor.createModel(INITIAL_CODE, 'css'),
    wordWrap: 'off',
    minimap: {
      enabled: false
    },
    scrollbar: {
      vertical: 'auto'
    }
  });

})
</script>

<style  scoped>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
.header {
  height: 40px;
  background-color: aliceblue;
}
.codeSide {
  width: 45vw;
  height: 90vh;
}
.code {
  /* width:100%; */
  height: 100%;
}
</style>

