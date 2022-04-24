<template>
  <div class="container">
      <div class="heading">
          <h3>Results:</h3>
      </div>
      <div class="results">
          <p>{{score}} ms You have {{rank}}</p>
      </div>
  </div>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null
        }
    },
    mounted() {
        if(this.score < 250){
           this.rank = "ninja fingers";
        } else if (this.score < 400) {
            this.rank = "rapid fingers";
        } else {
            this.rank = "snail fingers"
        }
    }
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