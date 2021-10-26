<template>
  <div>
    <p>{{ count }}</p>
  </div>
</template>

<script>
export default {
  props: ['count']
}

</script>

<style scoped>
div {
  background-color: lavender;
  width: 80px;
  height: 80px;
  display: flex;
  align-items: center; 
  justify-content: center;
  border-radius: 20px;
  font-size: large;
}
</style>
