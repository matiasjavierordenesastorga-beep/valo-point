[index.html](https://github.com/user-attachments/files/25454703/index.html)
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Último en Valorant</title>
</head>
<body>

  <h1>🏆 Contador del Último en Valorant</h1>

  <p>Matias: <span id="matias">0</span></p>
  <button onclick="sumar('matias')">+1 Matias</button>

  <p>Javier: <span id="javier">0</span></p>
  <button onclick="sumar('javier')">+1 Javier</button>

  <p>Jender: <span id="jender">0</span></p>
  <button onclick="sumar('jender')">+1 Jender</button>

  <br><br>
  <button onclick="resetear()">🔄 Resetear</button>

  <script>
    const jugadores = ['matias', 'javier', 'jender'];

    jugadores.forEach(nombre => {
      const guardado = localStorage.getItem(nombre);
      if (guardado !== null) {
        document.getElementById(nombre).innerText = guardado;
      }
    });

    function sumar(nombre) {
      let valor = document.getElementById(nombre);
      let nuevoValor = Number(valor.innerText) + 1;
      valor.innerText = nuevoValor;
      localStorage.setItem(nombre, nuevoValor);
    }

    function resetear() {
      if (confirm('¿Seguro que quieres resetear todo?')) {
        jugadores.forEach(nombre => {
          document.getElementById(nombre).innerText = 0;
          localStorage.setItem(nombre, 0);
        });
      }
    }
  </script>

</body>
</html>
