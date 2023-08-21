<script>
    // Dimensions
    const width = 800;
    const height = 100;
    const margin = { top: 5, right: 5, bottom: 5, left: 5 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;
  
    import { scaleLinear } from 'd3-scale';
    const scale = scaleLog().domain([0, 10]);
    

    // Array
    const values = [2, 4, 6, 7, 9];
  </script>


  <svg viewBox="0 0 {width} {height}">
    <g transform="translate({margin.left},{margin.top})">
    <g transform="translate({values})">

    <circle cx = {values} cy = {innerHeight / 2} r=10 />
      <!--  -->
    </g>
  </svg>
  

  