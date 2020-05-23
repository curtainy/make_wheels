<template>
  <div class="g-buttton-gruop">
    <slot></slot>
  </div>
</template>
<script>
export default {
  mounted(){
    for(let node of this.$el.children){
      if(node.nodeName.toLowerCase() !== 'button'){
        console.warn('g-button-group内的标签应该只包含g-button')
      }
    }
  }
}
</script>
<style scoped>
.g-buttton-gruop{
  display: inline-flex;
  vertical-align: middle;
}
.g-buttton-gruop .g-button{
  border-radius: 0;
  margin-left: -1px;
}
.g-buttton-gruop .g-button:first-child{
  border-top-left-radius: var(--border-radius);
  border-bottom-left-radius: var(--border-radius);
}
.g-buttton-gruop .g-button:last-child{
  border-top-right-radius: var(--border-radius);
  border-bottom-right-radius: var(--border-radius);
}
.g-buttton-gruop .g-button:hover{
  z-index: 1;
}
</style>