<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Catálogo de Perfumes</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }

    body {
      background: #f7f5f2;
      color: #222;
    }

    header {
      background: #111;
      color: white;
      text-align: center;
      padding: 30px 20px;
    }

    header h1 {
      font-size: 30px;
      margin-bottom: 8px;
    }

    header p {
      color: #d6d6d6;
    }

    .contenedor {
      max-width: 1100px;
      margin: auto;
      padding: 25px 18px;
    }

    .buscador {
      width: 100%;
      padding: 15px;
      border: 1px solid #ddd;
      border-radius: 12px;
      font-size: 16px;
      margin-bottom: 18px;
      outline: none;
    }

    .filtros {
      display: flex;
      gap: 10px;
      overflow-x: auto;
      margin-bottom: 25px;
    }

    .filtros button {
      border: none;
      padding: 10px 18px;
      border-radius: 20px;
      background: #ddd;
      cursor: pointer;
      white-space: nowrap;
    }

    .filtros button:hover {
      background: #bbb;
    }

    .catalogo {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 20px;
    }

    .producto {
      background: white;
      border-radius: 18px;
      overflow: hidden;
      box-shadow: 0 5px 18px rgba(0,0,0,.08);
      transition: .2s;
    }

    .producto:hover {
      transform: translateY(-4px);
    }

    .imagen {
      height: 230px;
      background: #eee;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #888;
      font-size: 18px;
    }

    .imagen img {
      width: 100%;
      height: 100%;
      object-fit: contain;
    }

    .info {
      padding: 18px;
    }

    .info h2 {
      font-size: 20px;
      margin-bottom: 7px;
    }

    .marca {
      color: #777;
      font-size: 14px;
      margin-bottom: 10px;
    }

    .descripcion {
      font-size: 14px;
      line-height: 1.5;
      color: #555;
      margin-bottom: 12px;
    }

    .precio {
      font-size: 23px;
      font-weight: bold;
      margin-bottom: 15px;
    }

    .comprar {
      display: block;
      text-align: center;
      text-decoration: none;
      background: #111;
      color: white;
      padding: 12px;
      border-radius: 10px;
      font-weight: bold;
    }

    .comprar:hover {
      background: #333;
    }

    footer {
      margin-top: 40px;
      padding: 25px;
      background: #111;
      color: white;
      text-align: center;
    }

    @media (max-width: 500px) {
      header h1 {
        font-size: 25px;
      }

      .catalogo {
        grid-template-columns: repeat(2, 1fr);
        gap: 12px;
      }

      .imagen {
        height: 170px;
      }

      .info {
        padding: 13px;
      }

      .info h2 {
        font-size: 17px;
      }

      .precio {
        font-size: 19px;
      }
    }
  </style>
</head>

<body>

<header>
  <h1>✨ Mi Catálogo de Perfumes</h1>
  <p>Encuentra tu aroma ideal</p>
</header>

<div class="contenedor">

  <input
    type="text"
    id="buscador"
    class="buscador"
    placeholder="🔎 Buscar perfume..."
    onkeyup="buscarPerfume()"
  >

  <div class="filtros">
    <button onclick="filtrar('todos')">Todos</button>
    <button onclick="filtrar('hombre')">Hombre</button>
    <button onclick="filtrar('mujer')">Mujer</button>
    <button onclick="filtrar('unisex')">Unisex</button>
  </div>

  <div class="catalogo">

    <!-- PERFUME 1 -->
    <div class="producto" data-categoria="hombre">
      <div class="imagen">
        <span>📸 Foto del perfume</span>
      </div>

      <div class="info">
        <h2>Dior Sauvage</h2>
        <p class="marca">Dior • Hombre</p>

        <p class="descripcion">
          Aroma fresco, elegante y masculino.
          Ideal para uso diario y ocasiones especiales.
        </p>

        <p class="precio">$850 MXN</p>

        <a
          class="comprar"
          href="https://wa.me/521XXXXXXXXXX?text=Hola,%20me%20interesa%20Dior%20Sauvage"
          target="_blank">
          Comprar por WhatsApp
        </a>
      </div>
    </div>

    <!-- PERFUME 2 -->
    <div class="producto" data-categoria="mujer">
      <div class="imagen">
        <span>📸 Foto del perfume</span>
      </div>

      <div class="info">
        <h2>Good Girl</h2>
        <p class="marca">Carolina Herrera • Mujer</p>

        <p class="descripcion">
          Fragancia elegante y dulce con un toque sofisticado.
        </p>

        <p class="precio">$950 MXN</p>

        <a
          class="comprar"
          href="https://wa.me/521XXXXXXXXXX?text=Hola,%20me%20interesa%20Good%20Girl"
          target="_blank">
          Comprar por WhatsApp
        </a>
      </div>
    </div>

    <!-- PERFUME 3 -->
    <div class="producto" data-categoria="unisex">
      <div class="imagen">
        <span>📸 Foto del perfume</span>
      </div>

      <div class="info">
        <h2>Club de Nuit</h2>
        <p class="marca">Armaf • Unisex</p>

        <p class="descripcion">
          Aroma intenso, elegante y de gran presencia.
        </p>

        <p class="precio">$750 MXN</p>

        <a
          class="comprar"
          href="https://wa.me/521XXXXXXXXXX?text=Hola,%20me%20interesa%20Club%20de%20Nuit"
          target="_blank">
          Comprar por WhatsApp
        </a>
      </div>
    </div>

    <!-- PERFUME 4 -->
    <div class="producto" data-categoria="hombre">
      <div class="imagen">
        <span>📸 Foto del perfume</span>
      </div>

      <div class="info">
        <h2>1 Million</h2>
        <p class="marca">Paco Rabanne • Hombre</p>

        <p class="descripcion">
          Fragancia intensa, dulce y llamativa.
        </p>

        <p class="precio">$900 MXN</p>

        <a
          class="comprar"
          href="https://wa.me/521XXXXXXXXXX?text=Hola,%20me%20interesa%201%20Million"
          target="_blank">
          Comprar por WhatsApp
        </a>
      </div>
    </div>

  </div>
</div>

<footer>
  <p>© 2026 Mi Catálogo de Perfumes</p>
  <p>✨ Calidad • Elegancia • Buen aroma ✨</p>
</footer>

<script>

function filtrar(categoria) {

  const productos = document.querySelectorAll(".producto");

  productos.forEach(producto => {

    if (categoria === "todos") {
      producto.style.display = "block";
    }

    else if (producto.dataset.categoria === categoria) {
      producto.style.display = "block";
    }

    else {
      producto.style.display = "none";
    }

  });

}

function buscarPerfume() {

  const texto = document
    .getElementById("buscador")
    .value
    .toLowerCase();

  const productos = document.querySelectorAll(".producto");

  productos.forEach(producto => {

    const nombre = producto
      .querySelector("h2")
      .textContent
      .toLowerCase();

    if (nombre.includes(texto)) {
      producto.style.display = "block";
    }

    else {
      producto.style.display = "none";
    }

  });

}

</script>

</body>
</html>
