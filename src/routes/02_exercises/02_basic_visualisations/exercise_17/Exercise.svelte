<script>
    // Dimensions
    const width = 800;
    const height = 100;
    const margin = { top: 5, right: 5, bottom: 5, left: 5 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;
  
    import { scaleLinear } from 'd3-scale';
    import { scaleLog } from 'd3-scale';

    // Array
    const values = [2, 4, 6, 7, 9];

    const xscale = scaleLog().
        domain([2, 9]).
        range([0, 3]);


  </script>

  <svg viewBox="0 0 {width/40} {height/2}">
    <g transform = "translate({margin.left},{margin.top})" >
      <!---  --->
      <circle cx={values[0]} cy={innerHeight / 4} r="2" />
      <circle cx={values[1]} cy={innerHeight / 4}  r="2" />
      <circle cx={values[2]} cy={innerHeight / 4} r="2" />
      <circle cx={values[3]} cy={innerHeight / 4}  r="2" />
      <circle cx={values[4]} cy={innerHeight / 4}  r="2" />

      <circle cx={xscale(values[0])} cy={innerHeight / 6} r="2" />
      <circle cx={xscale(values[1])} cy={innerHeight / 6} r="2" />
      <circle cx={xscale(values[2])} cy={innerHeight / 6} r="2" />
      <circle cx={xscale(values[3])} cy={innerHeight / 6} r="2" />
      <circle cx={xscale(values[4])} cy={innerHeight / 6} r="2" />

    </g>
  </svg>