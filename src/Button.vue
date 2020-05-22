<template>
  <button class="g-button" :class="{[`icon-${iconPosition}`]: true}">
    <g-icon :name="icon"></g-icon>
    <div class="content">
      <slot>按钮</slot>
    </div>
  </button>
</template>
<script>
export default {
  props: ['icon','iconPosition']
}
</script>
<style scoped>
  .g-button{
    font-size: var(--font-size);
    height: var(--button-height);
    padding: 0 1em;
    border-radius: var(--border-radius);
    border: 1px solid var(--border-color);
    background: var(--button-bg);
    display: inline-flex;
    justify-content: center;
    align-items: center;
  }
  .g-button:hover{
    border-color: var(--border-color-hover);
  }
  .g-button:active{
    background-color: var(--button-active-bg);
  }
  .g-button:focus{
    outline: none;
  }
  .g-button .icon{
    margin-right: 0.3em;
  }
  .icon-right .icon{
    order: 2;
  }
  .icon-right .content{
    order: 1;
  }
  .icon-right .icon{
    margin-right: 0;
    margin-left: 0.3em;
  }
</style>