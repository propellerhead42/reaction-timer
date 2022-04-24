<template>
  <div class="block">
     click me 
  </div>
</template>

<script>
export default {
    props: ["delay"]
}
</script>

<style>
    .block{
        display: flex;
        justify-content: center;
        align-items: center;
        width: 15rem;
        height: 15rem;
        margin-top: 2rem;
        background: red;
    }
</style>