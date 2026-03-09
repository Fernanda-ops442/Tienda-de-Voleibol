<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VoleiPro - Tu Tienda de Voleibol</title>
    <!-- Tailwind CSS para el diseño -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome para los íconos -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        vblue: {
                            DEFAULT: '#0047AB', // Azul clásico de voleibol
                            light: '#1A66D4',
                            dark: '#002E70'
                        },
                        vyellow: {
                            DEFAULT: '#FFDF00', // Amarillo clásico
                            hover: '#E6C800'
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        heading: ['Poppins', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Poppins:wght@500;600;700;800&display=swap');
        
        body {
            font-family: 'Inter', sans-serif;
        }
        h1, h2, h3, h4, .font-heading {
            font-family: 'Poppins', sans-serif;
        }
        
        /* Efecto parallax suave para el hero */
        .hero-bg {
            background-image: linear-gradient(rgba(0, 71, 171, 0.7), rgba(0, 46, 112, 0.8)), url('https://images.unsplash.com/photo-1592656094267-764a45160876?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
        }

        /* Ocultar scrollbar pero permitir scroll */
        .no-scrollbar::-webkit-scrollbar {
            display: none;
        }
        .no-scrollbar {
            -ms-overflow-style: none;  /* IE and Edge */
            scrollbar-width: none;  /* Firefox */
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800 antialiased">

    <!-- Navegación -->
    <nav class="bg-vblue text-white fixed w-full z-50 shadow-lg transition-all duration-300" id="navbar">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <!-- Logo -->
                <div class="flex-shrink-0 flex items-center cursor-pointer" onclick="window.scrollTo(0,0)">
                    <i class="fa-solid fa-volleyball text-vyellow text-3xl mr-2 animate-spin-slow" style="animation: spin 10s linear infinite;"></i>
                    <span class="font-heading font-bold text-2xl tracking-wider text-white">VOLEI<span class="text-vyellow">PRO</span></span>
                </div>
                
                <!-- Enlaces de escritorio -->
                <div class="hidden md:flex space-x-8 items-center">
                    <a href="#inicio" class="hover:text-vyellow transition font-medium">Inicio</a>
                    <a href="#especificaciones" class="hover:text-vyellow transition font-medium">El Deporte</a>
                    <a href="#tienda" class="hover:text-vyellow transition font-medium">Tienda</a>
                    
                    <!-- Carrito de compras -->
                    <button class="relative bg-vblue-dark p-3 rounded-full hover:bg-white hover:text-vblue transition group" onclick="toggleCart()">
                        <i class="fa-solid fa-cart-shopping"></i>
                        <span id="cart-count" class="absolute -top-1 -right-1 bg-vyellow text-vblue font-bold text-xs rounded-full h-5 w-5 flex items-center justify-center">0</span>
                    </button>
                </div>

                <!-- Botón menú móvil -->
                <div class="md:hidden flex items-center">
                    <button class="relative p-2 mr-4" onclick="toggleCart()">
                        <i class="fa-solid fa-cart-shopping text-xl"></i>
                        <span id="cart-count-mobile" class="absolute -top-1 -right-1 bg-vyellow text-vblue font-bold text-xs rounded-full h-5 w-5 flex items-center justify-center">0</span>
                    </button>
                    <button id="mobile-menu-btn" class="text-white hover:text-vyellow focus:outline-none">
                        <i class="fa-solid fa-bars text-2xl"></i>
                    </button>
                </div>
            </div>
        </div>
        
        <!-- Menú móvil -->
        <div id="mobile-menu" class="hidden md:hidden bg-vblue-dark pb-4">
            <a href="#inicio" class="block px-4 py-3 hover:bg-vblue text-white font-medium">Inicio</a>
            <a href="#especificaciones" class="block px-4 py-3 hover:bg-vblue text-white font-medium">El Deporte</a>
            <a href="#tienda" class="block px-4 py-3 hover:bg-vblue text-white font-medium">Tienda</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="inicio" class="hero-bg h-screen flex items-center justify-center text-center px-4 pt-20">
        <div class="max-w-4xl animate-fade-in-up">
            <span class="text-vyellow font-bold tracking-widest uppercase mb-4 block">Pasión en cada remate</span>
            <h1 class="text-5xl md:text-7xl font-heading font-extrabold text-white mb-6 drop-shadow-lg">
                Eleva tu Juego al <br><span class="text-transparent bg-clip-text bg-gradient-to-r from-vyellow to-yellow-200">Siguiente Nivel</span>
            </h1>
            <p class="text-lg md:text-xl text-gray-200 mb-10 max-w-2xl mx-auto drop-shadow-md">
                Equipamiento profesional, calzado especializado y accesorios para dominar la cancha. Siente la energía del voleibol.
            </p>
            <div class="flex flex-col sm:flex-row justify-center gap-4">
                <a href="#tienda" class="bg-vyellow hover:bg-vyellow-hover text-vblue font-bold py-4 px-8 rounded-full text-lg transition transform hover:-translate-y-1 hover:shadow-xl">
                    Ver Catálogo
                </a>
                <a href="#especificaciones" class="bg-transparent border-2 border-white text-white hover:bg-white hover:text-vblue font-bold py-4 px-8 rounded-full text-lg transition">
                    Reglas del Juego
                </a>
            </div>
        </div>
    </section>

    <!-- Especificaciones Section -->
    <section id="especificaciones" class="py-20 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16">
                <h2 class="text-3xl md:text-4xl font-heading font-bold text-vblue mb-4">Todo sobre el Voleibol</h2>
                <div class="w-24 h-1 bg-vyellow mx-auto rounded"></div>
                <p class="mt-6 text-gray-600 max-w-2xl mx-auto">Conoce las medidas y especificaciones oficiales dictadas por la FIVB (Federación Internacional de Voleibol).</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- Tarjeta Cancha -->
                <div class="bg-gray-50 rounded-2xl p-8 shadow-sm hover:shadow-xl transition-shadow border-t-4 border-vblue">
                    <div class="text-vblue text-4xl mb-4">
                        <i class="fa-solid fa-vector-square"></i>
                    </div>
                    <h3 class="text-xl font-heading font-bold mb-3">La Cancha</h3>
                    <ul class="text-gray-600 space-y-2">
                        <li><i class="fa-solid fa-check text-vyellow mr-2"></i><strong>Dimensiones:</strong> 18m de largo x 9m de ancho.</li>
                        <li><i class="fa-solid fa-check text-vyellow mr-2"></i><strong>Zona libre:</strong> Mínimo 3m a cada lado.</li>
                        <li><i class="fa-solid fa-check text-vyellow mr-2"></i><strong>Línea de ataque:</strong> A 3m de la red.</li>
                        <li><i class="fa-solid fa-check text-vyellow mr-2"></i><strong>Superficie:</strong> Plana, horizontal y uniforme.</li>
                    </ul>
                </div>

                <!-- Tarjeta Red -->
                <div class="bg-gray-50 rounded-2xl p-8 shadow-sm hover:shadow-xl transition-shadow border-t-4 border-vyellow">
                    <div class="text-vyellow text-4xl mb-4">
                        <i class="fa-solid fa-network-wired"></i>
                    </div>
                    <h3 class="text-xl font-heading font-bold mb-3">La Red</h3>
                    <ul class="text-gray-600 space-y-2">
                        <li><i class="fa-solid fa-check text-vblue mr-2"></i><strong>Altura Masculina:</strong> 2.43 metros.</li>
                        <li><i class="fa-solid fa-check text-vblue mr-2"></i><strong>Altura Femenina:</strong> 2.24 metros.</li>
                        <li><i class="fa-solid fa-check text-vblue mr-2"></i><strong>Ancho:</strong> 1 metro de ancho por 9.5-10m de largo.</li>
                        <li><i class="fa-solid fa-check text-vblue mr-2"></i><strong>Antenas:</strong> 1.80m de largo, sobresalen 80cm.</li>
                    </ul>
                </div>

                <!-- Tarjeta Balón -->
                <div class="bg-gray-50 rounded-2xl p-8 shadow-sm hover:shadow-xl transition-shadow border-t-4 border-vblue">
                    <div class="text-vblue text-4xl mb-4">
                        <i class="fa-solid fa-volleyball"></i>
                    </div>
                    <h3 class="text-xl font-heading font-bold mb-3">El Balón</h3>
                    <ul class="text-gray-600 space-y-2">
                        <li><i class="fa-solid fa-check text-vyellow mr-2"></i><strong>Forma:</strong> Esférica, cuero flexible o sintético.</li>
                        <li><i class="fa-solid fa-check text-vyellow mr-2"></i><strong>Circunferencia:</strong> Entre 65 y 67 cm.</li>
                        <li><i class="fa-solid fa-check text-vyellow mr-2"></i><strong>Peso:</strong> Entre 260 y 280 gramos.</li>
                        <li><i class="fa-solid fa-check text-vyellow mr-2"></i><strong>Presión:</strong> 0.30 a 0.325 kg/cm².</li>
                    </ul>
                </div>
            </div>

            <!-- Imagen representativa -->
            <div class="mt-16 rounded-2xl overflow-hidden shadow-2xl relative h-64 md:h-96">
                <img src="https://images.unsplash.com/photo-1547347298-4074fc3086f0?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="[Image of Cancha de Voleibol]" class="w-full h-full object-cover">
                <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent flex flex-col justify-end p-8 text-white">
                    <h3 class="text-2xl font-bold font-heading">El escenario de la gloria</h3>
                    <p class="text-gray-200">Cada centímetro de la cancha cuenta en el deporte más rápido del mundo.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Tienda Section -->
    <section id="tienda" class="py-20 bg-gray-100">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-end mb-12">
                <div>
                    <h2 class="text-3xl md:text-4xl font-heading font-bold text-vblue mb-4">Equipamiento Oficial</h2>
                    <div class="w-24 h-1 bg-vyellow rounded"></div>
                </div>
                <!-- Filtros rápidos -->
                <div class="hidden md:flex space-x-2">
                    <button class="px-4 py-2 bg-vblue text-white rounded-full text-sm font-medium">Todos</button>
                    <button class="px-4 py-2 bg-white text-gray-600 hover:bg-gray-200 rounded-full text-sm font-medium">Balones</button>
                    <button class="px-4 py-2 bg-white text-gray-600 hover:bg-gray-200 rounded-full text-sm font-medium">Protección</button>
                    <button class="px-4 py-2 bg-white text-gray-600 hover:bg-gray-200 rounded-full text-sm font-medium">Redes</button>
                </div>
            </div>

            <!-- Grid de Productos -->
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8" id="products-grid">
                <!-- Producto 1 -->
                <div class="bg-white rounded-2xl overflow-hidden shadow-md hover:shadow-2xl transition-all duration-300 group">
                    <div class="relative h-64 overflow-hidden bg-gray-200 flex items-center justify-center p-4">
                        <span class="absolute top-4 left-4 bg-red-500 text-white text-xs font-bold px-3 py-1 rounded-full z-10">Más vendido</span>
                        <img src="https://images.unsplash.com/photo-1612872087720-bb876e2e67d1?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500" onerror="this.src='https://placehold.co/600x400/0047AB/FFF?text=Balon+Oficial'">
                    </div>
                    <div class="p-6">
                        <div class="text-xs text-vblue font-bold tracking-wide uppercase mb-1">Balones</div>
                        <h3 class="text-lg font-heading font-bold text-gray-900 mb-2">Balón Pro FIVB Oficial</h3>
                        <p class="text-sm text-gray-500 mb-4 line-clamp-2">Balón de microfibra de alta calidad, diseñado para vuelo estable y máximo agarre.</p>
                        <div class="flex justify-between items-center">
                            <span class="text-xl font-bold text-vblue">$85.00</span>
                            <button onclick="addToCart('Balón Pro FIVB', 85.00)" class="bg-vblue text-white w-10 h-10 rounded-full flex items-center justify-center hover:bg-vyellow hover:text-vblue transition-colors">
                                <i class="fa-solid fa-plus"></i>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Producto 2 -->
                <div class="bg-white rounded-2xl overflow-hidden shadow-md hover:shadow-2xl transition-all duration-300 group">
                    <div class="relative h-64 overflow-hidden bg-gray-200 flex items-center justify-center">
                        <img src="https://images.unsplash.com/photo-1554224311-beee415c201f?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500" onerror="this.src='https://placehold.co/600x400/0047AB/FFF?text=Red+Profesional'">
                    </div>
                    <div class="p-6">
                        <div class="text-xs text-vblue font-bold tracking-wide uppercase mb-1">Equipamiento</div>
                        <h3 class="text-lg font-heading font-bold text-gray-900 mb-2">Red Competición con Antenas</h3>
                        <p class="text-sm text-gray-500 mb-4 line-clamp-2">Red de nylon ultra resistente con banda superior blanca y antenas oficiales incluidas.</p>
                        <div class="flex justify-between items-center">
                            <span class="text-xl font-bold text-vblue">$120.00</span>
                            <button onclick="addToCart('Red Competición', 120.00)" class="bg-vblue text-white w-10 h-10 rounded-full flex items-center justify-center hover:bg-vyellow hover:text-vblue transition-colors">
                                <i class="fa-solid fa-plus"></i>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Producto 3 -->
                <div class="bg-white rounded-2xl overflow-hidden shadow-md hover:shadow-2xl transition-all duration-300 group">
                    <div class="relative h-64 overflow-hidden bg-gray-200 flex items-center justify-center">
                        <img src="https://images.unsplash.com/photo-1608231387042-66d1773070a5?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500" onerror="this.src='https://placehold.co/600x400/0047AB/FFF?text=Zapatillas'">
                    </div>
                    <div class="p-6">
                        <div class="text-xs text-vblue font-bold tracking-wide uppercase mb-1">Calzado</div>
                        <h3 class="text-lg font-heading font-bold text-gray-900 mb-2">Zapatillas JumpMaster Max</h3>
                        <p class="text-sm text-gray-500 mb-4 line-clamp-2">Amortiguación superior para saltos altos y suela de goma para tracción perfecta.</p>
                        <div class="flex justify-between items-center">
                            <span class="text-xl font-bold text-vblue">$145.00</span>
                            <button onclick="addToCart('Zapatillas JumpMaster', 145.00)" class="bg-vblue text-white w-10 h-10 rounded-full flex items-center justify-center hover:bg-vyellow hover:text-vblue transition-colors">
                                <i class="fa-solid fa-plus"></i>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Producto 4 -->
                <div class="bg-white rounded-2xl overflow-hidden shadow-md hover:shadow-2xl transition-all duration-300 group">
                    <div class="relative h-64 overflow-hidden bg-gray-200 flex items-center justify-center">
                        <span class="absolute top-4 left-4 bg-vyellow text-vblue text-xs font-bold px-3 py-1 rounded-full z-10">Nuevo</span>
                        <!-- Usando un placeholder claro para rodilleras ya que es difícil encontrar específicas en unsplash general -->
                        <img src="https://placehold.co/600x400/F3F4F6/0047AB?text=Rodilleras+Elite+Gel" alt="" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500">
                    </div>
                    <div class="p-6">
                        <div class="text-xs text-vblue font-bold tracking-wide uppercase mb-1">Protección</div>
                        <h3 class="text-lg font-heading font-bold text-gray-900 mb-2">Rodilleras Elite Gel</h3>
                        <p class="text-sm text-gray-500 mb-4 line-clamp-2">Protección de gel de impacto lateral y frontal. Ajuste ergonómico que no resbala.</p>
                        <div class="flex justify-between items-center">
                            <span class="text-xl font-bold text-vblue">$35.00</span>
                            <button onclick="addToCart('Rodilleras Elite', 35.00)" class="bg-vblue text-white w-10 h-10 rounded-full flex items-center justify-center hover:bg-vyellow hover:text-vblue transition-colors">
                                <i class="fa-solid fa-plus"></i>
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Banner Motivacional -->
    <section class="bg-vblue text-white py-16 relative overflow-hidden">
        <!-- Decoración de fondo -->
        <div class="absolute top-0 right-0 -mr-20 -mt-20 opacity-10">
            <i class="fa-solid fa-volleyball text-9xl"></i>
        </div>
        <div class="absolute bottom-0 left-0 -ml-20 -mb-20 opacity-10">
            <i class="fa-solid fa-volleyball text-9xl"></i>
        </div>
        
        <div class="max-w-4xl mx-auto px-4 text-center relative z-10">
            <h2 class="text-3xl md:text-5xl font-heading font-bold mb-6">"El talento gana partidos, pero el trabajo en equipo gana campeonatos."</h2>
            <p class="text-vyellow text-xl font-medium">- Equipate y únete a tu equipo con lo mejor.</p>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-gray-300 py-12 border-t-4 border-vyellow">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 grid grid-cols-1 md:grid-cols-4 gap-8">
            <div class="col-span-1 md:col-span-1">
                <div class="flex items-center mb-4">
                    <i class="fa-solid fa-volleyball text-vyellow text-2xl mr-2"></i>
                    <span class="font-heading font-bold text-xl text-white">VOLEI<span class="text-vyellow">PRO</span></span>
                </div>
                <p class="text-sm text-gray-400 mb-4">La tienda definitiva para los amantes, jugadores y profesionales del voleibol.</p>
                <div class="flex space-x-4">
                    <a href="#" class="text-gray-400 hover:text-white transition"><i class="fa-brands fa-facebook text-xl"></i></a>
                    <a href="#" class="text-gray-400 hover:text-white transition"><i class="fa-brands fa-instagram text-xl"></i></a>
                    <a href="#" class="text-gray-400 hover:text-white transition"><i class="fa-brands fa-tiktok text-xl"></i></a>
                </div>
            </div>
            
            <div>
                <h4 class="text-white font-bold mb-4 font-heading">Enlaces Rápidos</h4>
                <ul class="space-y-2 text-sm">
                    <li><a href="#inicio" class="hover:text-vyellow transition">Inicio</a></li>
                    <li><a href="#especificaciones" class="hover:text-vyellow transition">Reglas e Historia</a></li>
                    <li><a href="#tienda" class="hover:text-vyellow transition">Tienda de Equipamiento</a></li>
                    <li><a href="#" class="hover:text-vyellow transition">Tallas y Guías</a></li>
                </ul>
            </div>
            
            <div>
                <h4 class="text-white font-bold mb-4 font-heading">Soporte</h4>
                <ul class="space-y-2 text-sm">
                    <li><a href="#" class="hover:text-vyellow transition">Envíos y Devoluciones</a></li>
                    <li><a href="#" class="hover:text-vyellow transition">Preguntas Frecuentes</a></li>
                    <li><a href="#" class="hover:text-vyellow transition">Contacto</a></li>
                    <li><a href="#" class="hover:text-vyellow transition">Términos de Servicio</a></li>
                </ul>
            </div>
            
            <div>
                <h4 class="text-white font-bold mb-4 font-heading">Boletín</h4>
                <p class="text-sm mb-4">Suscríbete para recibir ofertas y noticias de torneos.</p>
                <form class="flex" onsubmit="event.preventDefault(); alert('¡Gracias por suscribirte!');">
                    <input type="email" placeholder="Tu email" class="px-4 py-2 w-full rounded-l-md text-gray-900 focus:outline-none focus:ring-2 focus:ring-vyellow">
                    <button type="submit" class="bg-vyellow text-vblue px-4 py-2 rounded-r-md font-bold hover:bg-yellow-500 transition">
                        <i class="fa-solid fa-paper-plane"></i>
                    </button>
                </form>
            </div>
        </div>
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mt-12 pt-8 border-t border-gray-800 text-sm text-center text-gray-500">
            &copy; 2026 VoleiPro Store. Todos los derechos reservados.
        </div>
    </footer>

    <!-- Carrito Lateral (Off-canvas) -->
    <div id="cart-sidebar" class="fixed inset-y-0 right-0 w-full md:w-96 bg-white shadow-2xl transform translate-x-full transition-transform duration-300 z-[60] flex flex-col">
        <div class="bg-vblue text-white p-4 flex justify-between items-center shadow-md">
            <h2 class="font-heading font-bold text-xl flex items-center">
                <i class="fa-solid fa-cart-shopping mr-2 text-vyellow"></i> Tu Carrito
            </h2>
            <button onclick="toggleCart()" class="text-white hover:text-vyellow text-2xl focus:outline-none">
                <i class="fa-solid fa-xmark"></i>
            </button>
        </div>
        
        <div id="cart-items" class="flex-1 overflow-y-auto p-4 space-y-4">
            <!-- Los items del carrito se inyectan aquí via JS -->
            <div id="empty-cart-msg" class="text-center text-gray-500 mt-10 flex flex-col items-center">
                <i class="fa-solid fa-basket-shopping text-4xl mb-4 text-gray-300"></i>
                <p>Tu carrito está vacío.</p>
                <p class="text-sm mt-2">¡Añade algo de equipamiento para empezar a jugar!</p>
            </div>
        </div>
        
        <div class="border-t border-gray-200 p-4 bg-gray-50">
            <div class="flex justify-between items-center mb-4">
                <span class="font-bold text-gray-700">Total:</span>
                <span id="cart-total" class="font-heading font-bold text-2xl text-vblue">$0.00</span>
            </div>
            <button onclick="checkout()" class="w-full bg-vyellow hover:bg-yellow-500 text-vblue font-bold py-3 rounded-lg transition-colors flex justify-center items-center">
                Proceder al Pago <i class="fa-solid fa-arrow-right ml-2"></i>
            </button>
        </div>
    </div>

    <!-- Overlay oscuro para el carrito -->
    <div id="cart-overlay" class="fixed inset-0 bg-black/50 z-[55] hidden opacity-0 transition-opacity duration-300" onclick="toggleCart()"></div>

    <!-- Notificación Toast -->
    <div id="toast" class="fixed bottom-5 right-5 bg-green-500 text-white px-6 py-3 rounded-lg shadow-lg transform translate-y-20 opacity-0 transition-all duration-300 z-50 flex items-center">
        <i class="fa-solid fa-circle-check mr-2"></i>
        <span id="toast-message">Producto añadido al carrito</span>
    </div>

    <!-- JavaScript para interactividad -->
    <script>
        // Lógica del Navbar Móvil
        const mobileMenuBtn = document.getElementById('mobile-menu-btn');
        const mobileMenu = document.getElementById('mobile-menu');

        mobileMenuBtn.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });

        // Efecto scroll en Navbar
        window.addEventListener('scroll', () => {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 20) {
                navbar.classList.add('shadow-lg');
                navbar.style.backgroundColor = 'rgba(0, 71, 171, 0.95)';
            } else {
                navbar.classList.remove('shadow-lg');
                navbar.style.backgroundColor = '#0047AB';
            }
        });

        // Estado del Carrito
        let cart = [];
        const cartSidebar = document.getElementById('cart-sidebar');
        const cartOverlay = document.getElementById('cart-overlay');
        const cartItemsContainer = document.getElementById('cart-items');
        const emptyCartMsg = document.getElementById('empty-cart-msg');
        const cartTotalEl = document.getElementById('cart-total');
        const cartCountEl = document.getElementById('cart-count');
        const cartCountMobileEl = document.getElementById('cart-count-mobile');

        // Abrir/Cerrar Carrito
        function toggleCart() {
            const isClosed = cartSidebar.classList.contains('translate-x-full');
            if (isClosed) {
                cartSidebar.classList.remove('translate-x-full');
                cartOverlay.classList.remove('hidden');
                // Pequeño timeout para la animación de opacidad
                setTimeout(() => cartOverlay.classList.remove('opacity-0'), 10);
            } else {
                cartSidebar.classList.add('translate-x-full');
                cartOverlay.classList.add('opacity-0');
                setTimeout(() => cartOverlay.classList.add('hidden'), 300);
            }
        }

        // Añadir al Carrito
        function addToCart(name, price) {
            const existingItem = cart.find(item => item.name === name);
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({ name, price, quantity: 1 });
            }
            
            updateCartUI();
            showToast(`${name} añadido al carrito`);
        }

        // Eliminar del carrito
        function removeFromCart(index) {
            cart.splice(index, 1);
            updateCartUI();
        }

        // Modificar cantidad
        function changeQuantity(index, delta) {
            if (cart[index].quantity + delta > 0) {
                cart[index].quantity += delta;
            } else {
                removeFromCart(index);
                return;
            }
            updateCartUI();
        }

        // Actualizar Interfaz del Carrito
        function updateCartUI() {
            // Actualizar contadores (suma de cantidades)
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            cartCountEl.textContent = totalItems;
            cartCountMobileEl.textContent = totalItems;

            // Limpiar items anteriores (excepto el mensaje de vacío que controlaremos)
            cartItemsContainer.innerHTML = '';
            
            let total = 0;

            if (cart.length === 0) {
                cartItemsContainer.appendChild(emptyCartMsg);
                emptyCartMsg.style.display = 'flex';
            } else {
                // ocultar mensaje vacío original para no borrarlo del DOM
                emptyCartMsg.style.display = 'none'; 
                cartItemsContainer.appendChild(emptyCartMsg);

                cart.forEach((item, index) => {
                    total += item.price * item.quantity;
                    
                    const itemEl = document.createElement('div');
                    itemEl.className = 'flex justify-between items-center bg-gray-50 p-3 rounded-lg border border-gray-200';
                    itemEl.innerHTML = `
                        <div class="flex-1">
                            <h4 class="font-bold text-gray-800 text-sm">${item.name}</h4>
                            <div class="text-vblue font-bold">$${item.price.toFixed(2)}</div>
                        </div>
                        <div class="flex items-center space-x-2">
                            <button onclick="changeQuantity(${index}, -1)" class="w-6 h-6 bg-gray-200 rounded-full flex items-center justify-center hover:bg-gray-300 text-xs">
                                <i class="fa-solid fa-minus"></i>
                            </button>
                            <span class="w-4 text-center font-bold text-sm">${item.quantity}</span>
                            <button onclick="changeQuantity(${index}, 1)" class="w-6 h-6 bg-gray-200 rounded-full flex items-center justify-center hover:bg-gray-300 text-xs">
                                <i class="fa-solid fa-plus"></i>
                            </button>
                            <button onclick="removeFromCart(${index})" class="ml-2 text-red-500 hover:text-red-700 p-1">
                                <i class="fa-solid fa-trash"></i>
                            </button>
                        </div>
                    `;
                    cartItemsContainer.appendChild(itemEl);
                });
            }

            // Actualizar total
            cartTotalEl.textContent = `$${total.toFixed(2)}`;
        }

        // Sistema de Notificaciones (Toast)
        function showToast(message) {
            const toast = document.getElementById('toast');
            const toastMsg = document.getElementById('toast-message');
            
            toastMsg.textContent = message;
            
            // Mostrar
            toast.classList.remove('translate-y-20', 'opacity-0');
            
            // Ocultar después de 3 segundos
            setTimeout(() => {
                toast.classList.add('translate-y-20', 'opacity-0');
            }, 3000);
        }

        // Función de Checkout (Simulada)
        function checkout() {
            if (cart.length === 0) {
                alert("Tu carrito está vacío.");
                return;
            }
            
            // Reemplazar alert con ventana modal amigable generada por DOM
            const modalOverlay = document.createElement('div');
            modalOverlay.className = 'fixed inset-0 bg-black/80 z-[70] flex items-center justify-center p-4';
            
            const modalContent = document.createElement('div');
            modalContent.className = 'bg-white rounded-2xl p-8 max-w-sm w-full text-center transform scale-95 transition-transform duration-300';
            
            modalContent.innerHTML = `
                <div class="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-4 text-green-500 text-3xl">
                    <i class="fa-solid fa-check"></i>
                </div>
                <h3 class="text-2xl font-heading font-bold mb-2">¡Pedido Exitoso!</h3>
                <p class="text-gray-600 mb-6">Gracias por tu compra en VoleiPro. Prepararemos tu equipamiento pronto.</p>
                <button id="close-modal" class="bg-vblue text-white w-full py-3 rounded-lg font-bold hover:bg-vblue-light transition">
                    Cerrar
                </button>
            `;
            
            modalOverlay.appendChild(modalContent);
            document.body.appendChild(modalOverlay);
            
            // Animación de entrada al modal
            setTimeout(() => {
                modalContent.classList.remove('scale-95');
                modalContent.classList.add('scale-100');
            }, 10);
            
            // Limpiar carrito y cerrar modal
            document.getElementById('close-modal').addEventListener('click', () => {
                document.body.removeChild(modalOverlay);
                cart = [];
                updateCartUI();
                toggleCart();
            });
        }
    </script>
</body>
</html>
