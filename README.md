<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hertzz | Premium PC Components</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;700;900&family=Roboto:wght@300;400;500;700&display=swap');
        
        :root {
            --primary: #dc2626;
            --secondary: #6b7280;
            --dark: #000000;
            --light: #ffffff;
            --accent: #ef4444;
        }
        
        body {
            font-family: 'Roboto', sans-serif;
            background-color: var(--dark);
            color: var(--light);
            overflow-x: hidden;
        }
        
        h1, h2, h3, h4, .font-orbitron {
            font-family: 'Orbitron', sans-serif;
        }
        
        .gradient-text {
            background: linear-gradient(90deg, var(--primary), var(--accent));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .gradient-bg {
            background: linear-gradient(135deg, var(--primary), var(--accent));
        }
        
        .card-hover {
            transition: all 0.3s ease;
            transform-style: preserve-3d;
        }
        
        .card-hover:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 25px 50px -12px rgba(220, 38, 38, 0.25);
        }
        
        .glow {
            animation: glow 2s infinite alternate;
        }
        
        @keyframes glow {
            from {
                box-shadow: 0 0 5px var(--primary);
            }
            to {
                box-shadow: 0 0 20px var(--primary), 0 0 30px var(--accent);
            }
        }
        
        .float {
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0px); }
        }
        
        .pulse {
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { opacity: 1; }
            50% { opacity: 0.5; }
            100% { opacity: 1; }
        }
        
        .slide-in {
            animation: slideIn 1s forwards;
            opacity: 0;
        }
        
        @keyframes slideIn {
            from { transform: translateX(-50px); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }
        
        .product-card {
            perspective: 1000px;
        }
        
        .product-inner {
            transition: transform 0.8s;
            transform-style: preserve-3d;
        }
        
        .product-card:hover .product-inner {
            transform: rotateY(10deg);
        }
        
        .neon-border {
            position: relative;
        }
        
        .neon-border::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, var(--primary), var(--accent), var(--primary));
            z-index: -1;
            border-radius: inherit;
            opacity: 0;
            transition: opacity 0.3s;
        }
        
        .neon-border:hover::before {
            opacity: 1;
            animation: borderGlow 2s linear infinite;
        }
        
        @keyframes borderGlow {
            0% { filter: blur(5px); opacity: 0.7; }
            50% { filter: blur(7px); opacity: 1; }
            100% { filter: blur(5px); opacity: 0.7; }
        }
        
        .parallax {
            background-attachment: fixed;
            background-position: center;
            background-repeat: no-repeat;
            background-size: cover;
        }
    </style>
</head>
<body class="min-h-screen">
    <!-- Loading Animation -->
    <div id="loader" class="fixed inset-0 bg-black z-50 flex flex-col items-center justify-center transition-opacity duration-1000">
        <div class="w-32 h-32 border-4 border-t-transparent border-l-transparent border-r-red-500 border-b-gray-500 rounded-full animate-spin mb-4"></div>
        <h3 class="font-orbitron text-xl gradient-text">HERTZZ</h3>
        <p class="text-gray-400 mt-2">Loading premium experience...</p>
    </div>

    <!-- Navigation -->
    <nav class="fixed w-full z-40 bg-black bg-opacity-90 backdrop-filter backdrop-blur-lg border-b border-gray-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex items-center">
                    <div class="flex-shrink-0">
                        <h1 class="font-orbitron text-2xl gradient-text">HERTZZ</h1>
                    </div>
                    <div class="hidden md:block">
                        <div class="ml-10 flex items-baseline space-x-8">
                            <a href="#" class="text-white hover:text-red-500 px-3 py-2 rounded-md text-sm font-medium transition-all duration-300">Home</a>
                            <a href="#products" class="text-gray-300 hover:text-red-500 px-3 py-2 rounded-md text-sm font-medium transition-all duration-300">Products</a>
                            <a href="#features" class="text-gray-300 hover:text-red-500 px-3 py-2 rounded-md text-sm font-medium transition-all duration-300">Features</a>
                            <a href="#deals" class="text-gray-300 hover:text-red-500 px-3 py-2 rounded-md text-sm font-medium transition-all duration-300">Deals</a>
                            <a href="#contact" class="text-gray-300 hover:text-red-500 px-3 py-2 rounded-md text-sm font-medium transition-all duration-300">Contact</a>
                        </div>
                    </div>
                </div>
                <div class="hidden md:block">
                    <div class="ml-4 flex items-center md:ml-6">
                        <button class="p-1 rounded-full text-gray-400 hover:text-white focus:outline-none">
                            <i class="fas fa-search h-6 w-6"></i>
                        </button>
                        <button class="ml-3 p-1 rounded-full text-gray-400 hover:text-white focus:outline-none">
                            <i class="fas fa-shopping-cart h-6 w-6"></i>
                            <span class="absolute -mt-2 ml-3 bg-red-600 text-white text-xs font-bold px-1.5 py-0.5 rounded-full">3</span>
                        </button>
                        <button class="ml-3 p-1 rounded-full text-gray-400 hover:text-white focus:outline-none">
                            <i class="fas fa-user h-6 w-6"></i>
                        </button>
                    </div>
                </div>
                <div class="-mr-2 flex md:hidden">
                    <button type="button" class="bg-gray-900 inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-800 focus:outline-none">
                        <i class="fas fa-bars h-6 w-6"></i>
                    </button>
                </div>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="relative pt-32 pb-20 md:pt-40 px-4 sm:px-6 lg:px-8 overflow-hidden">
        <div class="absolute inset-0">
            <div class="absolute inset-0 bg-gradient-to-b from-black to-transparent z-10"></div>
            <div class="absolute inset-0 bg-black opacity-80 z-0"></div>
            <div class="absolute inset-0 z-0">
                <div class="absolute top-0 left-0 w-64 h-64 bg-red-500 rounded-full filter blur-3xl opacity-20 animate-pulse"></div>
                <div class="absolute bottom-0 right-0 w-64 h-64 bg-gray-600 rounded-full filter blur-3xl opacity-20 animate-pulse"></div>
            </div>
        </div>
        <div class="max-w-7xl mx-auto relative z-20">
            <div class="md:flex items-center">
                <div class="md:w-1/2 mb-10 md:mb-0 slide-in" style="animation-delay: 0.3s;">
                    <h1 class="text-4xl md:text-6xl font-orbitron font-bold mb-6">
                        <span class="gradient-text">Premium</span> <br>
                        <span class="text-white">PC Components</span>
                    </h1>
                    <p class="text-gray-300 mb-8 text-lg max-w-lg">
                        Experience the power of high-performance hardware. Precision engineering meets sleek design.
                    </p>
                    <div class="flex space-x-4">
                        <button class="gradient-bg text-white px-8 py-3 rounded-full font-medium hover:shadow-lg hover:shadow-red-500/30 transition-all duration-300 transform hover:scale-105">
                            Shop Now <i class="fas fa-arrow-right ml-2"></i>
                        </button>
                        <button class="border border-red-500 text-red-500 px-8 py-3 rounded-full font-medium hover:bg-red-500 hover:bg-opacity-10 transition-all duration-300 transform hover:scale-105">
                            Explore <i class="fas fa-chevron-down ml-2"></i>
                        </button>
                    </div>
                </div>
                <div class="md:w-1/2 relative float" style="animation-delay: 0.6s;">
                    <div class="relative max-w-md mx-auto">
                        <img src="https://images.unsplash.com/photo-1591488320449-011701bb6704?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Gaming PC" class="rounded-xl shadow-2xl glow">
                        <div class="absolute -bottom-6 -left-6 w-32 h-32 bg-gray-600 rounded-xl filter blur-xl opacity-30"></div>
                        <div class="absolute -top-6 -right-6 w-32 h-32 bg-red-500 rounded-xl filter blur-xl opacity-30"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Products -->
    <section id="products" class="py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-b from-black to-gray-900">
        <div class="max-w-7xl mx-auto">
            <div class="text-center mb-16 slide-in">
                <h2 class="text-3xl md:text-4xl font-orbitron font-bold mb-4">
                    <span class="gradient-text">Featured</span> <span class="text-white">Products</span>
                </h2>
                <p class="text-gray-400 max-w-2xl mx-auto">
                    Discover our curated selection of high-performance hardware designed for gamers, creators, and professionals.
                </p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <!-- Product 1 -->
                <div class="product-card">
                    <div class="product-inner bg-gray-800 rounded-xl overflow-hidden shadow-lg card-hover neon-border h-full flex flex-col">
                        <div class="relative pt-4 px-4">
                            <span class="absolute top-0 right-0 bg-red-600 text-white text-xs font-bold px-2 py-1 rounded-bl-lg">NEW</span>
                            <img src="https://images.unsplash.com/photo-1546054454-aa26e2b734c7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=880&q=80" alt="Mechanical Keyboard" class="w-full h-48 object-contain">
                        </div>
                        <div class="p-4 flex-grow">
                            <h3 class="text-xl font-bold text-white mb-2">Quantum X9 Keyboard</h3>
                            <p class="text-gray-400 text-sm mb-4">Optical-mechanical switches with RGB sync</p>
                            <div class="flex items-center mb-4">
                                <div class="flex text-yellow-400">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star-half-alt"></i>
                                </div>
                                <span class="text-gray-400 text-xs ml-2">(128 reviews)</span>
                            </div>
                        </div>
                        <div class="px-4 pb-4">
                            <div class="flex justify-between items-center">
                                <span class="text-2xl font-bold text-white">$149.99</span>
                                <button class="bg-red-500 hover:bg-red-600 text-white px-4 py-2 rounded-lg transition-all duration-300 transform hover:scale-105">
                                    <i class="fas fa-cart-plus"></i>
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Product 2 -->
                <div class="product-card">
                    <div class="product-inner bg-gray-800 rounded-xl overflow-hidden shadow-lg card-hover neon-border h-full flex flex-col">
                        <div class="relative pt-4 px-4">
                            <span class="absolute top-0 right-0 bg-red-500 text-white text-xs font-bold px-2 py-1 rounded-bl-lg">-20%</span>
                            <img src="https://images.unsplash.com/photo-1527814050087-3793815479db?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=728&q=80" alt="Gaming Mouse" class="w-full h-48 object-contain">
                        </div>
                        <div class="p-4 flex-grow">
                            <h3 class="text-xl font-bold text-white mb-2">Nebula R8 Mouse</h3>
                            <p class="text-gray-400 text-sm mb-4">16,000 DPI with weight tuning system</p>
                            <div class="flex items-center mb-4">
                                <div class="flex text-yellow-400">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                </div>
                                <span class="text-gray-400 text-xs ml-2">(256 reviews)</span>
                            </div>
                        </div>
                        <div class="px-4 pb-4">
                            <div class="flex justify-between items-center">
                                <div>
                                    <span class="text-gray-400 line-through text-sm">$89.99</span>
                                    <span class="text-2xl font-bold text-white ml-2">$71.99</span>
                                </div>
                                <button class="bg-red-500 hover:bg-red-600 text-white px-4 py-2 rounded-lg transition-all duration-300 transform hover:scale-105">
                                    <i class="fas fa-cart-plus"></i>
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Product 3 -->
                <div class="product-card">
                    <div class="product-inner bg-gray-800 rounded-xl overflow-hidden shadow-lg card-hover neon-border h-full flex flex-col">
                        <div class="relative pt-4 px-4">
                            <img src="https://images.unsplash.com/photo-1592155931584-901ac15763e3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1473&q=80" alt="Gaming Headset" class="w-full h-48 object-contain">
                        </div>
                        <div class="p-4 flex-grow">
                            <h3 class="text-xl font-bold text-white mb-2">Stellar H7 Headset</h3>
                            <p class="text-gray-400 text-sm mb-4">7.1 Surround Sound with ANC</p>
                            <div class="flex items-center mb-4">
                                <div class="flex text-yellow-400">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="far fa-star"></i>
                                </div>
                                <span class="text-gray-400 text-xs ml-2">(84 reviews)</span>
                            </div>
                        </div>
                        <div class="px-4 pb-4">
                            <div class="flex justify-between items-center">
                                <span class="text-2xl font-bold text-white">$129.99</span>
                                <button class="bg-red-500 hover:bg-red-600 text-white px-4 py-2 rounded-lg transition-all duration-300 transform hover:scale-105">
                                    <i class="fas fa-cart-plus"></i>
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Product 4 -->
                <div class="product-card">
                    <div class="product-inner bg-gray-800 rounded-xl overflow-hidden shadow-lg card-hover neon-border h-full flex flex-col">
                        <div class="relative pt-4 px-4">
                            <span class="absolute top-0 right-0 bg-red-500 text-white text-xs font-bold px-2 py-1 rounded-bl-lg">HOT</span>
                            <img src="https://images.unsplash.com/photo-1591488320449-011701bb6704?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Graphics Card" class="w-full h-48 object-contain">
                        </div>
                        <div class="p-4 flex-grow">
                            <h3 class="text-xl font-bold text-white mb-2">Titan RTX 4090</h3>
                            <p class="text-gray-400 text-sm mb-4">24GB GDDR6X, DLSS 3.0, Ray Tracing</p>
                            <div class="flex items-center mb-4">
                                <div class="flex text-yellow-400">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                </div>
                                <span class="text-gray-400 text-xs ml-2">(512 reviews)</span>
                            </div>
                        </div>
                        <div class="px-4 pb-4">
                            <div class="flex justify-between items-center">
                                <span class="text-2xl font-bold text-white">$1,599.99</span>
                                <button class="bg-red-500 hover:bg-red-600 text-white px-4 py-2 rounded-lg transition-all duration-300 transform hover:scale-105">
                                    <i class="fas fa-cart-plus"></i>
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="text-center mt-12">
                <button class="border border-red-500 text-red-500 px-8 py-3 rounded-full font-medium hover:bg-red-500 hover:bg-opacity-10 transition-all duration-300 transform hover:scale-105">
                    View All Products <i class="fas fa-chevron-right ml-2"></i>
                </button>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section id="features" class="py-20 px-4 sm:px-6 lg:px-8 bg-gray-900">
        <div class="max-w-7xl mx-auto">
            <div class="text-center mb-16">
                <h2 class="text-3xl md:text-4xl font-orbitron font-bold mb-4">
                    <span class="gradient-text">Why Choose</span> <span class="text-white">Hertzz?</span>
                </h2>
                <p class="text-gray-400 max-w-2xl mx-auto">
                    We're redefining the PC hardware experience with innovation, quality, and customer satisfaction at our core.
                </p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="bg-gray-800 rounded-xl p-6 hover:bg-gray-700 transition-all duration-500 transform hover:-translate-y-2">
                    <div class="w-16 h-16 gradient-bg rounded-lg flex items-center justify-center mb-6">
                        <i class="fas fa-rocket text-white text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-3">Cutting-Edge Performance</h3>
                    <p class="text-gray-400">
                        Our products are engineered with the latest technology to deliver unmatched speed, precision, and reliability.
                    </p>
                </div>
                
                <div class="bg-gray-800 rounded-xl p-6 hover:bg-gray-700 transition-all duration-500 transform hover:-translate-y-2">
                    <div class="w-16 h-16 gradient-bg rounded-lg flex items-center justify-center mb-6">
                        <i class="fas fa-award text-white text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-3">Premium Quality</h3>
                    <p class="text-gray-400">
                        Rigorously tested components built with premium materials for durability and long-lasting performance.
                    </p>
                </div>
                
                <div class="bg-gray-800 rounded-xl p-6 hover:bg-gray-700 transition-all duration-500 transform hover:-translate-y-2">
                    <div class="w-16 h-16 gradient-bg rounded-lg flex items-center justify-center mb-6">
                        <i class="fas fa-headset text-white text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-3">24/7 Support</h3>
                    <p class="text-gray-400">
                        Our expert support team is available around the clock to assist with any questions or technical issues.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Deals Section -->
    <section id="deals" class="py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-b from-gray-900 to-black">
        <div class="max-w-7xl mx-auto">
            <div class="text-center mb-16">
                <h2 class="text-3xl md:text-4xl font-orbitron font-bold mb-4">
                    <span class="gradient-text">Limited Time</span> <span class="text-white">Deals</span>
                </h2>
                <p class="text-gray-400 max-w-2xl mx-auto">
                    Don't miss these exclusive offers on our most popular products. Limited stock available!
                </p>
            </div>
            
            <div class="relative">
                <div class="absolute -left-16 top-1/2 transform -translate-y-1/2 w-32 h-32 bg-gray-600 rounded-full filter blur-3xl opacity-20"></div>
                <div class="absolute -right-16 top-1/2 transform -translate-y-1/2 w-32 h-32 bg-red-500 rounded-full filter blur-3xl opacity-20"></div>
                
                <div class="bg-gray-800 rounded-2xl overflow-hidden relative z-10">
                    <div class="md:flex">
                        <div class="md:w-1/2 p-8 md:p-12">
                            <span class="inline-block bg-red-500 text-white text-xs font-bold px-3 py-1 rounded-full mb-4">FLASH SALE</span>
                            <h3 class="text-3xl font-bold text-white mb-4">Galaxy S7 Speaker System</h3>
                            <p class="text-gray-400 mb-6">
                                Immerse yourself in crystal-clear 360° sound with our premium speaker system. Now with 30% off!
                            </p>
                            <div class="flex items-center mb-6">
                                <span class="text-gray-400 line-through text-xl mr-4">$299.99</span>
                                <span class="text-4xl font-bold gradient-text">$209.99</span>
                            </div>
                            <div class="mb-6">
                                <div class="flex justify-between text-sm text-gray-400 mb-1">
                                    <span>Offer ends in:</span>
                                    <span>12h 45m 22s</span>
                                </div>
                                <div class="w-full bg-gray-700 rounded-full h-2">
                                    <div class="bg-gradient-to-r from-red-500 to-gray-600 h-2 rounded-full" style="width: 65%"></div>
                                </div>
                            </div>
                            <button class="gradient-bg text-white px-8 py-3 rounded-full font-medium hover:shadow-lg hover:shadow-red-500/30 transition-all duration-300 transform hover:scale-105 w-full md:w-auto">
                                Get This Deal <i class="fas fa-bolt ml-2"></i>
                            </button>
                        </div>
                        <div class="md:w-1/2 relative">
                            <img src="https://images.unsplash.com/photo-1558379850-823f103f866a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Speaker System" class="w-full h-full object-cover">
                            <div class="absolute inset-0 bg-gradient-to-r from-gray-800 to-transparent md:bg-gradient-to-l md:from-gray-800 md:to-transparent opacity-80"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials -->
    <section class="py-20 px-4 sm:px-6 lg:px-8 bg-black">
        <div class="max-w-7xl mx-auto">
            <div class="text-center mb-16">
                <h2 class="text-3xl md:text-4xl font-orbitron font-bold mb-4">
                    <span class="gradient-text">What Our</span> <span class="text-white">Customers Say</span>
                </h2>
                <p class="text-gray-400 max-w-2xl mx-auto">
                    Don't just take our word for it. Here's what our community has to say about Hertzz.
                </p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="bg-gray-800 rounded-xl p-8 relative">
                    <div class="absolute -top-4 -left-4 w-16 h-16 gradient-bg rounded-full flex items-center justify-center">
                        <i class="fas fa-quote-left text-white text-xl"></i>
                    </div>
                    <p class="text-gray-300 mb-6">
                        "The Titan RTX 4090 transformed my gaming experience. Ray tracing at 4K has never looked this good!"
                    </p>
                    <div class="flex items-center">
                        <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="User" class="w-12 h-12 rounded-full mr-4">
                        <div>
                            <h4 class="text-white font-medium">Alex Johnson</h4>
                            <p class="text-red-400 text-sm">Professional Gamer</p>
                        </div>
                    </div>
                </div>
                
                <div class="bg-gray-800 rounded-xl p-8 relative">
                    <div class="absolute -top-4 -left-4 w-16 h-16 gradient-bg rounded-full flex items-center justify-center">
                        <i class="fas fa-quote-left text-white text-xl"></i>
                    </div>
                    <p class="text-gray-300 mb-6">
                        "As a video editor, the performance boost from Hertzz components has cut my render times in half."
                    </p>
                    <div class="flex items-center">
                        <img src="https://randomuser.me/api/portraits/women/44.jpg" alt="User" class="w-12 h-12 rounded-full mr-4">
                        <div>
                            <h4 class="text-white font-medium">Sarah Miller</h4>
                            <p class="text-red-400 text-sm">Video Editor</p>
                        </div>
                    </div>
                </div>
                
                <div class="bg-gray-800 rounded-xl p-8 relative">
                    <div class="absolute -top-4 -left-4 w-16 h-16 gradient-bg rounded-full flex items-center justify-center">
                        <i class="fas fa-quote-left text-white text-xl"></i>
                    </div>
                    <p class="text-gray-300 mb-6">
                        "The build quality of the Quantum X9 keyboard is exceptional. Typing feels like gliding on air."
                    </p>
                    <div class="flex items-center">
                        <img src="https://randomuser.me/api/portraits/men/75.jpg" alt="User" class="w-12 h-12 rounded-full mr-4">
                        <div>
                            <h4 class="text-white font-medium">Michael Chen</h4>
                            <p class="text-red-400 text-sm">Software Developer</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Newsletter -->
    <section class="py-16 px-4 sm:px-6 lg:px-8 bg-gradient-to-r from-red-900 to-gray-900">
        <div class="max-w-4xl mx-auto bg-black bg-opacity-40 backdrop-filter backdrop-blur-lg rounded-2xl p-8 md:p-12">
            <div class="md:flex items-center">
                <div class="md:w-1/2 mb-8 md:mb-0">
                    <h3 class="text-2xl font-bold text-white mb-2">Stay Updated</h3>
                    <p class="text-gray-300">
                        Subscribe to our newsletter for exclusive deals, new product launches, and tech insights.
                    </p>
                </div>
                <div class="md:w-1/2">
                    <form class="flex flex-col sm:flex-row gap-4">
                        <input type="email" placeholder="Your email address" class="flex-grow px-4 py-3 rounded-lg bg-gray-800 text-white focus:outline-none focus:ring-2 focus:ring-red-500">
                        <button class="gradient-bg text-white px-6 py-3 rounded-lg font-medium hover:shadow-lg hover:shadow-red-500/30 transition-all duration-300 transform hover:scale-105 whitespace-nowrap">
                            Subscribe <i class="fas fa-paper-plane ml-2"></i>
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact" class="bg-black py-12 px-4 sm:px-6 lg:px-8">
        <div class="max-w-7xl mx-auto">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8 mb-12">
                <div>
                    <h3 class="font-orbitron text-xl gradient-text mb-4">HERTZZ</h3>
                    <p class="text-gray-400 mb-4">
                        Pushing the boundaries of PC hardware technology since 2018.
                    </p>
                    <div class="flex space-x-4">
                        <a href="#" class="text-gray-400 hover:text-red-500 transition-colors duration-300">
                            <i class="fab fa-facebook-f"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-red-500 transition-colors duration-300">
                            <i class="fab fa-twitter"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-red-500 transition-colors duration-300">
                            <i class="fab fa-instagram"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-red-500 transition-colors duration-300">
                            <i class="fab fa-discord"></i>
                        </a>
                    </div>
                </div>
                
                <div>
                    <h4 class="text-white font-medium mb-4">Products</h4>
                    <ul class="space-y-2">
                        <li><a href="#" class="text-gray-400 hover:text-red-500 transition-colors duration-300">Keyboards</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-red-500 transition-colors duration-300">Mice</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-red-500 transition-colors duration-300">Headsets</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-red-500 transition-colors duration-300">Graphics Cards</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-red-500 transition-colors duration-300">Speakers</a></li>
                    </ul>
                </div>
                
                <div>
                    <h4 class="text-white font-medium mb-4">Support</h4>
                    <ul class="space-y-2">
                        <li><a href="#" class="text-gray-400 hover:text-red-500 transition-colors duration-300">Contact Us</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-red-500 transition-colors duration-300">FAQs</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-red-500 transition-colors duration-300">Shipping</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-red-500 transition-colors duration-300">Returns</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-red-500 transition-colors duration-300">Warranty</a></li>
                    </ul>
                </div>
                
                <div>
                    <h4 class="text-white font-medium mb-4">Contact</h4>
                    <ul class="space-y-2">
                        <li class="text-gray-400 flex items-center">
                            <i class="fas fa-map-marker-alt mr-2 text-red-500"></i> 123 Tech Street, Silicon Valley
                        </li>
                        <li class="text-gray-400 flex items-center">
                            <i class="fas fa-phone-alt mr-2 text-red-500"></i> +1 (555) 123-4567
                        </li>
                        <li class="text-gray-400 flex items-center">
                            <i class="fas fa-envelope mr-2 text-red-500"></i> support@hertzz.com
                        </li>
                    </ul>
                </div>
            </div>
            
            <div class="border-t border-gray-800 pt-8 flex flex-col md:flex-row justify-between items-center">
                <p class="text-gray-500 text-sm mb-4 md:mb-0">
                    &copy; 2023 Hertzz. All rights reserved.
                </p>
                <div class="flex space-x-6">
                    <a href="#" class="text-gray-500 hover:text-gray-300 text-sm">Privacy Policy</a>
                    <a href="#" class="text-gray-500 hover:text-gray-300 text-sm">Terms of Service</a>
                    <a href="#" class="text-gray-500 hover:text-gray-300 text-sm">Cookies</a>
                </div>
            </div>
        </div>
    </footer>

    <!-- Back to Top -->
    <button id="backToTop" class="fixed bottom-8 right-8 w-12 h-12 gradient-bg rounded-full flex items-center justify-center text-white shadow-lg transition-opacity duration-300 opacity-0 invisible">
        <i class="fas fa-arrow-up"></i>
    </button>

    <script>
        // Hide loader when page is loaded
        window.addEventListener('load', function() {
            setTimeout(function() {
                document.getElementById('loader').style.opacity = '0';
                setTimeout(function() {
                    document.getElementById('loader').style.display = 'none';
                }, 1000);
            }, 1500);
            
            // Animate elements on scroll
            const animateOnScroll = function() {
                const elements = document.querySelectorAll('.slide-in');
                elements.forEach(element => {
                    const elementPosition = element.getBoundingClientRect().top;
                    const windowHeight = window.innerHeight;
                    
                    if (elementPosition < windowHeight - 100) {
                        element.style.animation = `slideIn 0.6s forwards ${element.dataset.delay || '0s'}`;
                    }
                });
            };
            
            // Run once on load
            animateOnScroll();
            
            // Run on scroll
            window.addEventListener('scroll', animateOnScroll);
            
            // Back to top button
            const backToTopButton = document.getElementById('backToTop');
            
            window.addEventListener('scroll', function() {
                if (window.pageYOffset > 300) {
                    backToTopButton.style.opacity = '1';
                    backToTopButton.style.visibility = 'visible';
                } else {
                    backToTopButton.style.opacity = '0';
                    backToTopButton.style.visibility = 'hidden';
                }
            });
            
            backToTopButton.addEventListener('click', function() {
                window.scrollTo({
                    top: 0,
                    behavior: 'smooth'
                });
            });
            
            // Product card hover effect
            const productCards = document.querySelectorAll('.product-card');
            productCards.forEach(card => {
                card.addEventListener('mouseenter', function() {
                    this.querySelector('.product-inner').style.transform = 'rotateY(10deg)';
                });
                
                card.addEventListener('mouseleave', function() {
                    this.querySelector('.product-inner').style.transform = 'rotateY(0)';
                });
            });
            
            // Add to cart animation
            const addToCartButtons = document.querySelectorAll('[class*="fa-cart-plus"]');
            addToCartButtons.forEach(button => {
                button.addEventListener('click', function(e) {
                    e.preventDefault();
                    const cartIcon = document.querySelector('.fa-shopping-cart');
                    
                    // Create flying item animation
                    const flyingItem = document.createElement('div');
                    flyingItem.innerHTML = '<i class="fas fa-microchip text-red-500"></i>';
                    flyingItem.style.position = 'fixed';
                    flyingItem.style.left = `${e.clientX}px`;
                    flyingItem.style.top = `${e.clientY}px`;
                    flyingItem.style.fontSize = '20px';
                    flyingItem.style.transition = 'all 0.8s cubic-bezier(0.68, -0.55, 0.265, 1.55)';
                    flyingItem.style.zIndex = '9999';
                    document.body.appendChild(flyingItem);
                    
                    const cartPosition = cartIcon.getBoundingClientRect();
                    
                    setTimeout(() => {
                        flyingItem.style.left = `${cartPosition.left + cartPosition.width/2}px`;
                        flyingItem.style.top = `${cartPosition.top + cartPosition.height/2}px`;
                        flyingItem.style.opacity = '0';
                        flyingItem.style.transform = 'scale(0.2)';
                    }, 10);
                    
                    setTimeout(() => {
                        flyingItem.remove();
                        
                        // Update cart count
                        const cartCount = document.querySelector('.fa-shopping-cart + span');
                        if (cartCount) {
                            const currentCount = parseInt(cartCount.textContent.match(/\d+/)[0]);
                            cartCount.textContent = `(${currentCount + 1})`;
                            
                            // Pulse animation
                            cartCount.classList.add('animate-ping');
                            setTimeout(() => {
                                cartCount.classList.remove('animate-ping');
                            }, 500);
                        }
                    }, 800);
                });
            });
        });
    </script>
</body>
</html>
