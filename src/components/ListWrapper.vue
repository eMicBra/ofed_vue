<style scoped>
.listWrapper > ul {
  display: block;
  max-width: 30%;
}
</style>
<template>
  <div class="listWrapper">
    <h3>
      <slot name="list-title">No List Title Slotted In</slot>
    </h3>
    <slot name="list">
      <ul>
        <li>no</li>
        <li>list</li>
        <li>slotted</li>
        <li>in</li>
      </ul>
    </slot>
  </div>
</template>
<script>
export default {
  name: 'ListWrapper'
};
</script>
