<script>
    import * as d3 from "d3"
  
    export let numbers = []
  
    function alturaColBooks(n) {
      let scale = d3
        .scaleLinear()
        .domain([0, d3.max(numbers)]) // extent returns [min, max]
        .range([0, 100])
      return scale(n)
    }
  
  </script>
  
  
  <div class="books-container">
    {#each numbers as n}
    <div>
      <div class="column-wrapper">
        <div class="column-books" style="height: {alturaColBooks(n)}%;"></div>
        <img class="books" src="./images/books.png" alt="">
      </div>
      <p class="number">{n}</p>
    </div>
    {/each}
  </div>
  
  <style>
    .books-container {
      display: flex;
    }
    .column-wrapper {
      position: relative;
      width: 160px;
      height: 190px;
      background-color: #d4d4d4;
      margin-bottom: 10%;
      margin-top: 10%;
      /*border: black 1px solid; */
    }
    .column-books {
      position: absolute;
      height: 50%;
      left: 10%;
      right: 10%;
      bottom: 0;
      /* width: 100%; */
      background-color: #2BD127;
    }
    .books {
      position: absolute;
      bottom: -10px;
      width: 100%;
    }
    .number {
      text-align: center;

    }
  </style>
  