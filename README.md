<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ZENITH-REST™ | Equilibrium Solutions</title>
<style>
    /* --- ESTÉTICA: MINIMALISTA & ORGÁNICA --- */
    @import url('https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600&display=swap');

    :root {
        --bg-body: #ffffff;
        --bg-soft: #f8fafc;
        --primary-blue: #e0f2fe; /* Calma */
        --text-main: #475569;
        --text-dark: #1e293b;
        --accent-sage: #84a98c; /* Sustentabilidad/Kapok */
        --accent-earth: #d6ccc2; 
        --shadow: 0 10px 30px -10px rgba(0,0,0,0.1);
        --price-color: #008000;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Outfit', sans-serif; }
    
    body { 
        background-color: var(--bg-body); 
        color: var(--text-main); 
        line-height: 1.7;
        overflow-x: hidden;
    }

    /* --- HEADER --- */
    header {
        position: sticky; top: 0; z-index: 1000;
        background: rgba(255,255,255,0.9);
        backdrop-filter: blur(10px);
        padding: 15px 5%;
        display: flex; justify-content: space-between; align-items: center;
        border-bottom: 1px solid #f1f5f9;
    }
    
    .logo { font-size: 1.3rem; font-weight: 600; color: var(--text-dark); letter-spacing: 1px; }
    .logo span { color: var(--accent-sage); }
    
    nav { display: flex; gap: 20px; }
    nav a { text-decoration: none; color: var(--text-main); font-size: 0.9rem; transition: 0.3s; } 
    @media(max-width: 768px) { nav { display: none; } } /* Ocultar menú en móviles */

    .icons { display: flex; gap: 15px; font-size: 1.2rem; cursor: pointer; }

    /* --- HERO (Simulación de Ondas) --- */
    .hero {
        height: 85vh;
        position: relative;
        display: flex; flex-direction: column; justify-content: center; align-items: center;
        text-align: center; padding: 20px;
        background: radial-gradient(circle, #f0f9ff 0%, #fff 70%);
        overflow: hidden;
    }

    /* Animación de Ondas CSS */
    .wave {
        position: absolute; width: 600px; height: 600px;
        border: 1px solid var(--primary-blue); border-radius: 50%;
        opacity: 0; animation: ripple 6s infinite linear;
    }
    .wave:nth-child(2) { animation-delay: 2s; }
    .wave:nth-child(3) { animation-delay: 4s; }

    @keyframes ripple {
        0% { transform: scale(0.5); opacity: 0.8; border-width: 10px; }
        100% { transform: scale(2.5); opacity: 0; border-width: 0px; }
    }

    .hero-content { z-index: 2; max-width: 700px; animation: fadeUp 1s ease; }
    .hero h1 { font-size: 3rem; margin-bottom: 15px; color: var(--text-dark); line-height: 1.1; }
    .hero p { font-size: 1.2rem; margin-bottom: 30px; color: #64748b; }
    
    .btn {
        padding: 12px 30px; border-radius: 50px; text-decoration: none; 
        font-weight: 600; border: none; cursor: pointer; transition: 0.3s; display: inline-block;
    }
    .btn-primary { background: var(--text-dark); color: white; }
    .btn-primary:hover { background: var(--accent-sage); transform: translateY(-3px); }
    .btn-outline { border: 1px solid var(--text-dark); color: var(--text-dark); background: transparent; margin-left: 10px; }

    /* --- SECCIONES GENERALES --- */
    .section { padding: 80px 5%; max-width: 1200px; margin: 0 auto; }
    .title { text-align: center; margin-bottom: 50px; font-size: 2rem; color: var(--text-dark); }
    
    .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 30px; }
    
    .card {
        background: white; padding: 30px; border-radius: 20px;
        box-shadow: var(--shadow); border: 1px solid #f8fafc;
        transition: transform 0.3s;
    }
    .card:hover { transform: translateY(-5px); }
    .card-icon { font-size: 2.5rem; margin-bottom: 15px; display: block; }

    /* --- INNOVACIÓN --- */
    .innovation-box { background: var(--bg-soft); padding: 40px; border-radius: 20px; display: flex; flex-wrap: wrap; gap: 40px; align-items: center; }
    .thermo-bar { width: 100%; height: 15px; background: linear-gradient(90deg, #3b82f6, #e0f2fe, #ef4444); border-radius: 10px; position: relative; margin-top: 20px;}
    .indicator { width: 20px; height: 20px; background: var(--accent-sage); border-radius: 50%; position: absolute; top: -2.5px; left: 50%; animation: float 3s infinite ease-in-out; border: 2px solid white; }
    @keyframes float { 0%, 100% { left: 45%; } 50% { left: 55%; } }

    /* --- IMPACTO SOCIAL --- */
    .impact-section .grid .card { 
        border: 1px solid #e0f2fe; 
        background: var(--bg-soft); 
        text-align: center;
        display: flex; flex-direction: column; justify-content: space-between;
    }
    
    /* --- UDG EVENTO (Diseño Local) --- */
    .udg-section {
        background-color: var(--accent-sage);
        color: white;
        border-radius: 25px;
        padding: 60px 30px;
        text-align: center;
        position: relative;
        overflow: hidden;
    }
    .udg-tag { background: white; color: var(--accent-sage); padding: 5px 15px; border-radius: 20px; font-weight: bold; font-size: 0.8rem; display: inline-block; margin-bottom: 15px; }
    .udg-discount { font-size: 3rem; font-weight: 700; margin: 20px 0; }

    /* --- SHOP & CHECKOUT --- */
    .product-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        gap: 30px;
        margin-top: 40px;
    }
    .product-card {
        background: var(--bg-soft);
        border-radius: 15px;
        overflow: hidden;
        box-shadow: var(--shadow);
        border: 1px solid #e2e8f0;
        display: flex;
        flex-direction: column;
        transition: transform 0.3s;
    }
    .product-card:hover { transform: translateY(-5px); }
    .product-card img {
        width: 100%;
        height: 220px;
        object-fit: cover; 
        background-color: #eef; 
        padding: 20px;
        transition: transform 0.3s;
    }
    .product-card:hover img { transform: scale(1.02); }

    .product-info { padding: 20px; flex-grow: 1; display: flex; flex-direction: column; }
    .product-name { font-size: 1.3rem; color: var(--text-dark); margin-bottom: 8px; }
    .product-desc { font-size: 0.9rem; color: #64748b; flex-grow: 1; }
    .price { font-size: 1.8rem; color: var(--price-color); font-weight: 600; margin-top: 15px; }


    /* --- MODAL --- */
    .modal-overlay {
        display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
        background: rgba(0,0,0,0.6); z-index: 2000; justify-content: center; align-items: center;
        backdrop-filter: blur(5px);
    }
    .modal-box {
        background: white; padding: 40px; border-radius: 20px; width: 90%; max-width: 450px;
        animation: slideUp 0.3s ease;
    }
    @keyframes slideUp { from { opacity:0; transform:translateY(20px); } to { opacity:1; transform:translateY(0); } }

    .row { display: flex; justify-content: space-between; padding: 10px 0; border-bottom: 1px solid #eee; }
    .donation-highlight { background: #f0fdf4; padding: 12px; border-radius: 8px; color: #166534; font-weight: 600; margin: 15px 0; border: 1px solid #bbf7d0; }

</style>
</head>
<body>

<header>
    <div class="logo">ZENITH-<span>REST™</span></div>
    <nav>
        <a href="#hero">Inicio</a>
        <a href="#ciencia">Ciencia</a>
        <a href="#sustentabilidad">Sustentabilidad</a>
        <a href="#impacto">Impacto Social</a>
        <a href="#comprar">Comprar</a>
    </nav>
    <div class="icons">
        <span>🔍</span>
        <span onclick="openCart('normal', 'ZENITH-REST™ Original')">🛒</span>
    </div>
</header>

<section class="hero" id="hero">
    <div class="wave"></div>
    <div class="wave"></div>
    <div class="wave"></div>
    <div class="hero-content">
        <h1>ZENITH-REST: La ciencia de la serenidad.</h1>
        <p>"Tu noche en equilibrio. Tu día en plenitud."</p>
        <div>
            <a href="#comprar" class="btn btn-primary">Comprar Ahora</a>
            <a href="#ciencia" class="btn btn-outline">Descubre la Tecnología</a>
        </div>
    </div>
</section>

<section id="ciencia" class="section">
    <h2 class="title">Equilibrio Térmico Perfecto</h2>
    <div class="innovation-box">
        <div style="flex: 1; min-width: 300px;">
            <h3>Termostato Natural</h3>
            <p style="margin: 15px 0;">Despídete del calor nocturno. Nuestro núcleo de <strong>PCM Biológico + Kapok</strong> absorbe el exceso de temperatura y lo libera cuando la habitación se enfría.</p>
            <small style="color: #888;">GRÁFICO DE REGULACIÓN ACTIVA</small>
            <div class="thermo-bar"><div class="indicator"></div></div>
            <div style="display: flex; justify-content: space-between; font-size: 0.8rem; margin-top: 5px; color: #888;"><span>Frío</span><span>Calor</span></div>
        </div>
    </div>
</section>

<section id="sustentabilidad" class="section">
    <h2 class="title">Sueño Profundo, Huella Ligera</h2>
    <div class="grid">
        <div class="card">
            <span class="card-icon">🌿</span>
            <h3>Kapok Orgánico</h3>
            <p>Seda vegetal hipoalergénica. Cosecha ética sin dañar árboles.</p>
        </div>
        <div class="card">
            <span class="card-icon">♻️</span>
            <h3>Ciclo Cerrado</h3>
            <p>Trueque Consciente: Envíanos tu almohada vieja y reciclamos todo.</p>
        </div>
        <div class="card">
            <span class="card-icon">🎋</span>
            <h3>Bambú y Grafeno</h3>
            <p>Tejidos avanzados que conducen el calor, son antibacterianos y resistentes.</p>
        </div>
    </div>
</section>

<section id="impacto" class="section impact-section">
    <h2 class="title">Dormir bien para hacer el bien.</h2>
    <div class="grid">
        <div class="card">
            <span class="card-icon" style="color: #16a34a;">🏡</span>
            <h3>Compromiso de Donación (Santuario de Sueño)</h3>
            <p>Un porcentaje de cada venta se destina a la **climatización sustentable** de hogares o escuelas vulnerables (techos verdes y ventilación pasiva).</p>
        </div>
        <div class="card">
            <span class="card-icon" style="color: #f59e0b;">👨‍🌾</span>
            <h3>Programa Padrino de Productores (P3)</h3>
            <p>Apadrina un lote de Kapok. Recibe un video del agricultor y un descuento en tu próxima compra si financias su segundo lote.</p>
            <a href="#" class="btn btn-outline" style="border-color: var(--accent-sage); color: var(--accent-sage);">Conoce a nuestros Padrinos</a>
        </div>
    </div>
</section>


<section id="eventos" class="section">
    <div class="udg-section">
        <span class="udg-tag">VISITA PREPA 15 "CINCO DE MAYO"</span>
        <h2>ZENITH-REST en tu Comunidad</h2>
        <p style="max-width: 600px; margin: 15px auto;">Apoya a la UDG 15. El 50% de las ganancias de esta promo se donan directamente para climatizar el campus.</p>
        <div class="udg-discount">-15% OFF</div>
        <button class="btn" style="background: white; color: var(--accent-sage);" onclick="openCart('udg', 'ZENITH-REST™ UDG Promo')">Canjear Oferta UDG</button>
    </div>
</section>

<section id="comprar" class="section">
    <h2 class="title">Nuestra Colección de Almohadas</h2>
    <div class="product-grid">
        
        <div class="product-card">
            <img src="https://i.imgur.com/your-zenith-rest-original-pillow-image.jpg" alt="Almohada ZENITH-REST™ Original"> 
            
            <div class="product-info">
                <h3 class="product-name">ZENITH-REST™ Original</h3>
                <p class="product-desc">Control de calor activo, el original. Equilibrio térmico con Kapok orgánico y PCM biológico.</p>
                <div class="price">$129.99</div>
                <button class="btn btn-primary" onclick="openCart('normal', 'ZENITH-REST™ Original')">Añadir al Carrito</button>
            </div>
        </div>
        
        <div class="product-card">
            <img src="https://i.imgur.com/your-zenith-rest-grafeno-plus-pillow-image.jpg" alt="Almohada ZENITH-REST™ Grafeno Plus">
            
            <div class="product-info">
                <h3 class="product-name">ZENITH-REST™ Grafeno Plus</h3>
                <p class="product-desc">Dispersión de calor superior y soporte ergonómico. Con grafeno y memoria adaptativa.</p>
                <div class="price">$159.99</div>
                <button class="btn btn-primary" onclick="openCart('normal', 'ZENITH-REST™ Grafeno Plus')">Añadir al Carrito</button>
            </div>
        </div>

    </div>
</section>

<div class="modal-overlay" id="cartModal">
    <div class="modal-box">
        <h3 style="margin-bottom: 20px; color: var(--text-dark);">Tu Carrito de Compras</h3>
        <div id="cartItems">
            <div class="row"><span>ZENITH-REST™ Original</span><span>$129.99</span></div>
        </div>
        <div class="row" style="font-weight: 600; font-size: 1.1rem; margin-top: 20px; border-top: 1px solid #ddd;">
            <span>Total:</span><span id="cartTotal">$129.99</span>
        </div>
        <div class="donation-highlight">
            🎉 ¡Tu compra nos ayuda a climatizar escuelas!
        </div>
        <button class="btn btn-primary" style="width: 100%; margin-top: 20px;">Finalizar Compra</button>
        <button class="btn btn-outline" style="width: 100%; margin-top: 10px;" onclick="closeCart()">Seguir Comprando</button>
    </div>
</div>


<script>
    // JS para la funcionalidad básica del carrito (añadir y abrir/cerrar modal)
    let cart = [];
    let udgPromoActive = false;

    function openCart(promoType, productName) {
        udgPromoActive = (promoType === 'udg');
        
        // Simular añadir un producto (simplificado para el ejemplo)
        if (productName) {
            let price = 0;
            if (productName === 'ZENITH-REST™ Original') {
                price = 129.99;
            } else if (productName === 'ZENITH-REST™ Grafeno Plus') {
                price = 159.99;
            } else if (productName === 'ZENITH-REST™ UDG Promo') {
                price = 129.99 * 0.85; // Aplica 15% de descuento
            }

            // Evitar duplicados simples si el mismo botón se presiona varias veces
            const existingItem = cart.find(item => item.name === productName);
            if (existingItem) {
                existingItem.quantity++;
            } else {
                cart.push({ name: productName, price: price, quantity: 1 });
            }
        }
        
        updateCartDisplay();
        document.getElementById('cartModal').style.display = 'flex';
    }

    function updateCartDisplay() {
        const cartItemsContainer = document.getElementById('cartItems');
        cartItemsContainer.innerHTML = '';
        let total = 0;

        cart.forEach(item => {
            const itemElement = document.createElement('div');
            itemElement.classList.add('row');
            itemElement.innerHTML = `<span>${item.name} (${item.quantity})</span><span>$${(item.price * item.quantity).toFixed(2)}</span>`;
            cartItemsContainer.appendChild(itemElement);
            total += item.price * item.quantity;
        });

        document.getElementById('cartTotal').textContent = `$${total.toFixed(2)}`;
    }


    function closeCart() {
        document.getElementById('cartModal').style.display = 'none';
        cart = []; // Vaciar carrito al cerrar para este ejemplo simplificado
    }
</script>

</body>
</html>
