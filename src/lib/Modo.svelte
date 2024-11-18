<script>
    let darkMode = false;
  
    // Función para alternar entre modo oscuro y claro
    const toggleBackground = () => {
      darkMode = !darkMode;
    };
  </script>
  
  <style>
    /* Definimos el estilo de cada modo */
    .light {
      background-color: white;
      color: black;
    }
    .dark {
      background-color: black;
      color: white;
    }
  </style>
  
  <div class="{darkMode ? 'dark' : 'light'}">
    <button on:click={toggleBackground}>
      Cambiar Fondo
    </button>
    <h1>Esto cambia el color de fondo</h1>
  </div>