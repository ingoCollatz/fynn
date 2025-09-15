<script lang="ts">
  export let size: string = "40";
  export let className: string = "";
</script>

<svg 
  width={size} 
  height={size} 
  viewBox="0 0 320 55" 
  class={className}
  xmlns="http://www.w3.org/2000/svg"
>
  <!-- House Icon -->
  <g transform="translate(5, 5)">
    <!-- House outline -->
    <path d="M5 20 L5 35 L25 35 L25 20 L15 10 Z" 
          stroke="#1B5E20" stroke-width="2" fill="none"/>
    
    <!-- Roof -->
    <path d="M2 20 L15 7 L28 20" 
          stroke="#1B5E20" stroke-width="2" fill="none" stroke-linejoin="round"/>
    
    <!-- Window -->
    <rect x="8" y="16" width="6" height="6" 
          fill="none" stroke="#1B5E20" stroke-width="1"/>
    <line x1="11" y1="16" x2="11" y2="22" stroke="#1B5E20" stroke-width="0.5"/>
    <line x1="8" y1="19" x2="14" y2="19" stroke="#1B5E20" stroke-width="0.5"/>
    
    <!-- Door -->
    <rect x="18" y="26" width="4" height="9" 
          fill="none" stroke="#1B5E20" stroke-width="1"/>
  </g>
  
  <!-- Leaf -->
  <g transform="translate(35, 10)">
    <ellipse cx="3" cy="8" rx="4" ry="2" fill="#1B5E20" transform="rotate(-30 3 8)"/>
    <ellipse cx="8" cy="12" rx="3" ry="1.5" fill="#1B5E20" transform="rotate(20 8 12)"/>
    <rect x="5" y="15" width="1" height="10" fill="#1B5E20"/>
  </g>
  
  <!-- Company Name -->
  <text x="60" y="25" 
        font-family="Arial, sans-serif" 
        font-weight="900" 
        font-size="22" 
        fill="#1B5E20">FYNN SCHOMANN</text>
        
  <text x="60" y="42" 
        font-family="Arial, sans-serif" 
        font-weight="600" 
        font-size="12" 
        fill="#1B5E20">HAUSMEISTERSERVICE &amp; GARTENPFLEGE</text>
</svg>