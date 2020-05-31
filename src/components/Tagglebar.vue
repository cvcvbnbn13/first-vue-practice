<template>
  <div>
    <b-button v-b-toggle.sidebar-right>沒事可以按我</b-button>
    <b-sidebar id="sidebar-right" title="啊 彈出來了" right shadow>
      <div class="px-3 py-2">
        <p>
          單純看到一個功能覺得很有趣就把它放進來了。
        </p>
        <b-img src="https://picsum.photos/500/500/?image=54" fluid thumbnail></b-img>
      </div>
    </b-sidebar>
  </div>
</template>