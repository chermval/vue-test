<template id="userCard">
	<div class="card">
    <h5 class="card-header element-header">{{ name }}</h5>
    
    <div class="card-body element-body">
      <h5 class="card-title color-body">{{  website }}</h5>
      <p class="card-text color-body">{{  email }}</p>
    </div>
    
  </div>
</template>

<script>

export default {
  name: 'user-card',
  template: '#userCard',
  props: ['name', 'email', 'website']
}

</script>


<style lang="less">

/* Mixin */
@base: #663333;
@blank: #ffffff;

@lighten1: lighten(@base, 15%);



/* Implementation */

.element-header  {
  text-align: center;
  background-color: @base;
  color: @blank;
}

.element-body  {
  background-color: @lighten1;
  color: @blank;
}

 

</style>