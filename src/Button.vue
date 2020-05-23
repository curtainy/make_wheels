<template>
  <button class="g-button" 
         :class="{[`icon-${iconPosition}`]: true}">
    <g-icon :name="icon" class="icon" v-if="icon && !isLoading"></g-icon>
    <g-icon name="loading" :class="{loading:isLoading}" class="icon" v-if="isLoading"></g-icon>
    <div class="content">
      <slot>按钮</slot>
    </div>
  </button>
</template>
<script>
export default {
  props: {
    icon: {
      type: String,
      default: undefined
    },
    iconPosition: {
      type: String,
      default: undefined
    },
    isLoading: {
      type: Boolean,
      default: false
    }
  }
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
    vertical-align: middle;
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

  @keyframes rotate {
    0%{
      transform: rotate(0deg);
    }
    100%{
      transform: rotate(360deg);
    }
  }

  .loading{
    animation: rotate 1s linear infinite;
  }

</style>