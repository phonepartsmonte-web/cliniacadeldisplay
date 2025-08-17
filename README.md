<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Clínica del Display</title>
  <style>
    :root {
      --primary: #ff3333;
      --dark: #111;
      --light: #fff;
    }
    body { font-family: Arial, sans-serif; margin: 0; padding: 0; background-color: var(--dark); color: var(--light); }
    header { background: #000; color: var(--light); padding: 1rem; display: flex; justify-content: space-between; align-items: center; border-bottom: 2px solid var(--primary); }
    header img { height: 60px; }
    nav a { margin: 0 1rem; color: var(--primary); text-decoration: none; font-weight: bold; }
    nav a:hover { color: var(--light); }
    section { padding: 2rem; }
    footer { background: #000; color: var(--light); text-align: center; padding: 1rem; border-top: 2px solid var(--primary); }
    .btn { display: inline-block; padding: 10px 20px; background: var(--primary); color: white; text-decoration: none; border-radius: 5px; font-weight: bold; }
    .btn:hover { background: #d62e2e; }
    .section-dark { background-color: #222; }

    /* Catalogo */
    .catalog { display: flex; justify-content: space-around; flex-wrap: wrap; }
    .catalog-item { background: #333; border-radius: 8px; padding: 1rem; margin: 1rem; text-align: center; box-shadow: 0 0 10px rgba(0,0,0,0.3); width: 250px; }
    .catalog-item img { max-width: 100%; border-radius: 5px; margin-bottom: 1rem; }
    .catalog-item h3 { color: var(--primary); }

    /* Slider */
    .slider { position: relative; overflow: hidden; height: 500px; }
    .slides { display: flex; transition: transform 0.5s ease-in-out; height: 100%; }
    .slide { min-width: 100%; height: 100%; position: relative; }
    .slide img { width: 100%; height: 100%; object-fit: cover; }
    .caption { position: absolute; bottom: 20px; left: 20px; background: rgba(0,0,0,0.6); padding: 1rem; border-radius: 8px; }
    .caption h2 { margin: 0; color: var(--primary); }
    .slider-btn { position: absolute; top: 50%; transform: translateY(-50%); background: rgba(0,0,0,0.5); border: none; color: white; font-size: 2rem; cursor: pointer; padding: 0.5rem; border-radius: 50%; }
    .prev { left: 10px; }
    .next { right: 10px; }
    .dots { text-align: center; position: absolute; bottom: 15px; width: 100%; }
    .dot { height: 12px; width: 12px; margin: 0 5px; background-color: rgba(255,255,255,0.5); border-radius: 50%; display: inline-block; cursor: pointer; transition: background 0.3s ease; }
    .dot.active, .dot:hover { background-color: var(--primary); }

    /* Buscador */
    #buscador { width: 80%; padding: 10px; margin: 20px auto; display: block; border-radius: 5px; border: none; font-size: 1rem; }
  </style>
</head>
<body>
  <header>
    <img src="https://i.imgur.com/6pN4K7N.png" alt="Logo Clínica del Display">
    <nav>
      <a href="#inicio">Inicio</a>
      <a href="#nosotros">Quiénes somos</a>
      <a href="#servicios">Servicios</a>
      <a href="#catalogo">Catálogo</a>
      <a href="#contacto">Contacto</a>
    </nav>
  </header>

  <!-- SLIDER -->
  <section id="inicio">
    <div class="slider">
      <div class="slides" id="slides">
        <div class="slide">
          <img src="https://www.apple.com/v/iphone-15-pro/f/images/overview/welcome/hero__cj6i78tzkp8i_large_2x.jpg" alt="Promo iPhone 15">
          <div class="caption">
            <h2>🔥 iPhone 15 Pro</h2>
            <p>El smartphone más potente de Apple</p>
            <a href="https://wa.me/573005137436?text=Estoy%20interesado%20en%20el%20iPhone%2015%20Pro" class="btn">Comprar ahora</a>
          </div>
        </div>
        <div class="slide">
          <img src="https://www.apple.com/v/iphone-14-pro/f/images/overview/hero/hero__gnfk5g59t0qe_large_2x.jpg" alt="Promo iPhone 14">
          <div class="caption">
            <h2>✨ iPhone 14 Pro</h2>
            <p>Innovación al alcance de tu mano</p>
            <a href="https://wa.me/573005137436?text=Estoy%20interesado%20en%20el%20iPhone%2014%20Pro" class="btn">Ver más</a>
          </div>
        </div>
        <div class="slide">
          <img src="https://www.apple.com/v/iphone-13/f/images/overview/hero/hero__dvsxv8smkkgi_large_2x.jpg" alt="Promo iPhone 13">
          <div class="caption">
            <h2>📱 iPhone 13</h2>
            <p>Gran rendimiento a mejor precio</p>
            <a href="https://wa.me/573005137436?text=Estoy%20interesado%20en%20el%20iPhone%2013" class="btn">Comprar</a>
          </div>
        </div>
      </div>
      <button class="slider-btn prev" onclick="moverSlide(-1)">&#10094;</button>
      <button class="slider-btn next" onclick="moverSlide(1)">&#10095;</button>
      <div class="dots" id="dots">
        <span class="dot active" onclick="irASlide(0)"></span>
        <span class="dot" onclick="irASlide(1)"></span>
        <span class="dot" onclick="irASlide(2)"></span>
      </div>
    </div>
  </section>

  <!-- NOSOTROS -->
  <section id="nosotros">
    <h2>Quiénes somos</h2>
    <p><strong>Clínica del Display</strong> es una empresa fundada en 2019 con el objetivo de brindar la mejor atención y calidad en equipos electrónicos, tanto nuevos como usados.</p>
  </section>

  <!-- SERVICIOS -->
  <section id="servicios" class="section-dark">
    <h2>Servicios</h2>
    <ul>
      <li>📱 Servicio técnico especializado multimarca.</li>
      <li>🆕 Venta de equipos nuevos.</li>
      <li>🔁 Venta de equipos usados certificados.</li>
      <li>🛠️ Repuestos y accesorios originales.</li>
    </ul>
  </section>

  <!-- CATALOGO -->
  <section id="catalogo">
    <h2>Catálogo</h2>
    <input type="text" id="buscador" placeholder="🔍 Buscar iPhone..." onkeyup="buscarProducto()">
    <div class="catalog" id="productos">
      <!-- Ejemplo: iPhone 11 -->
      <div class="catalog-item">
        <img src="https://store.storeimages.cdn-apple.com/4668/as-images.apple.com/is/refurb-iphone11-black-2019?wid=2000&hei=2000&fmt=jpeg&qlt=95" alt="iPhone 11">
        <h3>iPhone 11</h3>
        <p>Precio: $2,000,000</p>
      </div>
      <!-- iPhone 12 -->
      <div class="catalog-item">
        <img src="https://store.storeimages.cdn-apple.com/4668/as-images.apple.com/is/refurb-iphone-12-black-2020?wid=2000&hei=2000&fmt=jpeg&qlt=95" alt="iPhone 12">
        <h3>iPhone 12</h3>
        <p>Precio: $2,800,000</p>
      </div>
      <!-- iPhone 13 -->
      <div class="catalog-item">
        <img src="https://store.storeimages.cdn-apple.com/4668/as-images.apple.com/is/iphone-13-blue-select-2021?wid=2000&hei=2000&fmt=jpeg&qlt=95" alt="iPhone 13">
        <h3>iPhone 13</h3>
        <p>Precio: $3,200,000</p>
      </div>
      <!-- iPhone 14 -->
      <div class="catalog-item">
        <img src="https://store.storeimages.cdn-apple.com/4668/as-images.apple.com/is/iphone-14-blue-select-202209?wid=2000&hei=2000&fmt=jpeg&qlt=95" alt="iPhone 14">
        <h3>iPhone 14</h3>
        <p>Precio: $3,800,000</p>
      </div>
      <!-- iPhone 15 -->
      <div class="catalog-item">
        <img src="https://store.storeimages.cdn-apple.com/4668/as-images.apple.com/is/iphone-15-blue-select-202309?wid=2000&hei=2000&fmt=jpeg&qlt=95" alt="iPhone 15">
        <h3>iPhone 15</h3>
        <p>Precio: $4,200,000</p>
      </div>
      <!-- iPhone 16 -->
      <div class="catalog-item">
        <img src="https://fdn2.gsmarena.com/vv/bigpic/apple-iphone-16.jpg" alt="iPhone 16">
        <h3>iPhone 16</h3>
        <p>Precio: $4,800,000</p>
      </div>
      <!-- iPhone 16 Pro -->
      <div class="catalog-item">
        <img src="https://fdn2.gsmarena.com/vv/bigpic/apple-iphone-16-pro.jpg" alt="iPhone 16 Pro">
        <h3>iPhone 16 Pro</h3>
        <p>Precio: $5,500,000</p>
      </div>
      <!-- iPhone 16 Pro Max -->
      <div class="catalog-item">
        <img src="https://fdn2.gsmarena.com/vv/bigpic/apple-iphone-16-pro-max.jpg" alt="iPhone 16 Pro Max">
        <h3>iPhone 16 Pro Max</h3>
        <p>Precio: $6,200,000</p>
      </div>
    </div>
  </section>

  <!-- CONTACTO -->
  <section id="contacto" class="section-dark">
    <h2>Contacto</h2>
    <p>📍 Dirección: Av. Ejemplo 123, Ciudad</p>
    <p>📞 Teléfono: 3005137436</p>
    <p>📱 <a class="btn" href="https://wa.me/573005137436" target="_blank">Escribinos por WhatsApp</a></p>
    <p>📧 Email: contacto@clinicadeldisplay.com</p>
  </section>

  <footer>
    <p>&copy; 2025 Clínica del Display. Todos los derechos reservados.</p>
  </footer>

  <script>
    // SLIDER
    let indice = 0;
    const slides = document.getElementById("slides");
    const dots = document.querySelectorAll(".dot");

    function mostrarSlide(n) {
      const totalSlides = slides.children.length;
      if (n >= totalSlides) indice = 0;
      if (n < 0) indice = totalSlides - 1;
      slides.style.transform = `translateX(${-indice * 100}%)`;

      dots.forEach(dot => dot.classList.remove("active"));
      dots[indice].classList.add("active");
    }

    function moverSlide(n) {
      indice += n;
      mostrarSlide(indice);
    }

    function irASlide(n) {
      indice = n;
      mostrarSlide(indice);
    }

    setInterval(() => {
      moverSlide(1);
    }, 5000);

    // BUSCADOR
    function buscarProducto() {
      let input = document.getElementById("buscador").value.toLowerCase();
      let items = document.querySelectorAll(".catalog-item");
      items.forEach(item => {
        let nombre = item.querySelector("h3").innerText.toLowerCase();
        item.style.display = nombre.includes(input) ? "block" : "none";
      });
    }
  </script>
</body>
</html>

