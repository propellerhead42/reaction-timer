<template>
  <div class="container">
      <div class="heading">
          <h3>Results:</h3>
      </div>
      <div class="results">
          <p>{{score}} ms</p>
      </div>
  </div>
</template>

<script>
export default {
    props: ['score']
}
</script>

<style lang="scss">

    .container {
        display: flex;
        flex-direction: column;
        width: 100%;
    }

    .heading {
        border-bottom: 1px solid black;

        h3 {
            margin-left: 1rem;
        }
    }

    .results {
        display: flex;
        flex-wrap: wrap;


        p {
            min-width: 3rem;
            padding: 0.5rem;
            margin: 1rem;
            background: gray;
            text-align: center;
            font-weight: 500;
            font-size: 1.25rem;
            color: white;
        }
    }


</style>