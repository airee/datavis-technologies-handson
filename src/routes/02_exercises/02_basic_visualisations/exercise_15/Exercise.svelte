<script>
    const width = 100;
    const height = 100;
    const margin = { top: 5, right: 5, bottom: 5, left: 5 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;
    const cx = innerWidth / 2;
    const cy = innerHeight / 2;
  </script>
  
  <svg {width} {height}>
    <g transform="translate({margin.left}, {margin.top})">
      <circle {cx} {cy} r={cx} />
      <rect x=0 y=0 width=10 height=10 />
    </g>
  </svg>
  
  <style>
    svg {
      border: 1px solid black;
      border-radius: 5px;
    }

    rect {
      fill: yellow;
    }

    circle {
      fill: skyblue;
    }

  </style>
  