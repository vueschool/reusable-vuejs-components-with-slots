<template>
  <button><slot></slot></button>
</template>

<script>
export default {};
</script>


<style scoped>
button {
  color: white;
  display: flex;
  align-items: center;
  padding: 0.25rem 0.5rem;
  border: none;
  text-transform: uppercase;
  font-weight: bold;
  background-color: #41b883;
  border-radius: 0.25rem;
  line-height: 1.5;
  margin: 10px;
}
</style>