<!-- Script JS -->
<script>
    import * as d3 from "d3"
    import BooksColumns from "./lib/BooksColumns.svelte"
  
    let numbers = [5, 18, 29, 75, 100]
    let numbersDivided5 = numbers.map(n => Math.floor(n / 5))
  
    function altura(n) {
      let scale = d3
        .scaleLinear()
        .domain(d3.extent(numbers)) // extent returns [min, max]
        .range([15, 225])
      return scale(n)
    }
</script>

<!-- Estilos-->
<main>
    <h3 class="headline">Meta de Lectura Anual</h3>
    <BooksColumns numbers={numbers} />
    
</main>

<style>
    .headline {
      text-align: left;
      margin-top: 50px;
      /* border: 1px solid red; */
    }
  </style>

<!-- Estructura contenido HTML CLASE 1 
<h1>Meta de Lectura Anual</h1>
<br>
<div>
    <h5 id="mes">Mayo 2023</h5>
    <h5 id="mes">Diciembre 2023</h5>
</div>

<div>
    <img src="public\images\libros.svg" alt="librosMayo" width=20%>
    <img src="public\images\libros1.svg" alt="librosDiciembre" width=20%>
</div>
<div>
    <h5 id="porcentaje"> 25%</h5>
    <h5 id="porcentaje">100%</h5>
</div>
 -->

