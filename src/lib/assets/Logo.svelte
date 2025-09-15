<script lang="ts">
  export let size: string = "120";
  export let className: string = "";
</script>

<svg 
  width={size} 
  height={size} 
  viewBox="0 0 600 150" 
  class={className}
  xmlns="http://www.w3.org/2000/svg"
>
  <!-- House -->
  <g transform="translate(20, 20)" fill="#1B5E20">
    <!-- House outline -->
    <path d="M10 40 L10 80 L50 80 L50 40 L30 20 Z" stroke="#1B5E20" stroke-width="4" fill="none"/>
    
    <!-- Roof -->
    <path d="M5 40 L30 15 L55 40" stroke="#1B5E20" stroke-width="4" fill="none" stroke-linejoin="round"/>
    
    <!-- Chimney -->
    <rect x="40" y="25" width="6" height="15" fill="#1B5E20"/>
    
    <!-- Window (4 panes) -->
    <g>
      <!-- Window frame -->
      <rect x="16" y="30" width="12" height="12" fill="none" stroke="#1B5E20" stroke-width="2"/>
      <!-- Cross divider -->
      <line x1="22" y1="30" x2="22" y2="42" stroke="#1B5E20" stroke-width="1"/>
      <line x1="16" y1="36" x2="28" y2="36" stroke="#1B5E20" stroke-width="1"/>
    </g>
    
    <!-- Door -->
    <rect x="35" y="60" width="8" height="20" fill="none" stroke="#1B5E20" stroke-width="2"/>
    <circle cx="40" cy="70" r="1" fill="#1B5E20"/>
  </g>
  
  <!-- Plant with leaves -->
  <g transform="translate(80, 30)">
    <!-- Main stem -->
    <rect x="12" y="40" width="3" height="35" fill="#1B5E20"/>
    
    <!-- Large leaf (left) -->
    <ellipse cx="5" cy="35" rx="10" ry="6" fill="#1B5E20" transform="rotate(-45 5 35)"/>
    
    <!-- Medium leaf (right) -->
    <ellipse cx="22" cy="45" rx="8" ry="4" fill="#1B5E20" transform="rotate(30 22 45)"/>
    
    <!-- Small leaf (left lower) -->
    <ellipse cx="3" cy="55" rx="6" ry="3" fill="#1B5E20" transform="rotate(-60 3 55)"/>
  </g>
  
  <!-- Curved ground line connecting all elements -->
  <path d="M10 110 Q80 100 150 110" stroke="#1B5E20" stroke-width="3" fill="none"/>
  
  <!-- Company Name - Horizontal Layout -->
  <text x="180" y="50" 
        font-family="Arial, sans-serif" 
        font-weight="900" 
        font-size="36" 
        fill="#1B5E20">FYNN SCHOMANN</text>
  
  <!-- Service Description -->
  <text x="180" y="80" 
        font-family="Arial, sans-serif" 
        font-weight="600" 
        font-size="14" 
        fill="#1B5E20">HAUSMEISTERSERVICE UND GARTENPFLEGE</text>
</svg>