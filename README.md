<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Your Destiny Has Been Written</title>
    <meta name="description" content="The Definitive Word Ministry - Your Destiny Has Been Written. Discover God's plan through prophetic teaching, life coaching, and transformative resources.">
    <meta name="keywords" content="prophetic teaching, life coaching, Christian resources, destiny, ministry, South Africa">
    <meta name="author" content="The Definitive Word Ministry">
    <meta property="og:title" content="The Definitive Word - Your Destiny Has Been Written">
    <meta property="og:description" content="Discover God's plan for your life through prophetic teaching and life coaching">
    <meta property="og:image" content="https://yourdomain.com/images/og-image.jpg">
    <meta property="og:url" content="https://yourdomain.com">
    <meta property="og:type" content="website">
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="The Definitive Word - Your Destiny Has Been Written">
    <meta name="twitter:description" content="Discover God's plan for your life through prophetic teaching and life coaching">
    <meta name="csrf-token" content="csrf_token_placeholder">
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://js.stripe.com/v3/"></script>
    
    <style>
        :root {
            --prophetic-blue: #1e3a8a;
            --prophetic-red: #dc2626;
            --prophetic-gold: #d4af37;
            --white: #ffffff;
            --light-gray: #f3f4f6;
            --dark-gray: #374151;
            --success: #10b981;
            --warning: #f59e0b;
            --error: #ef4444;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #f9fafb;
            color: var(--dark-gray);
            line-height: 1.6;
        }

        /* Header & Navigation */
        header {
            background: linear-gradient(135deg, var(--prophetic-blue), var(--prophetic-red));
            color: var(--white);
            padding: 0.5rem 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 1.5rem;
        }

        .logo {
            display: flex;
            flex-direction: column;
        }

        .logo h1 {
            font-size: 1.6rem;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .logo p {
            font-size: 0.8rem;
            font-style: italic;
            opacity: 0.9;
        }

        .nav-container {
            display: flex;
            align-items: center;
            gap: 1.5rem;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 1.5rem;
            align-items: center;
        }

        .nav-links a {
            color: var(--white);
            text-decoration: none;
            font-weight: 500;
            transition: opacity 0.3s;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 0.9rem;
            white-space: nowrap;
        }

        .nav-links a:hover {
            opacity: 0.8;
        }

        .user-actions {
            display: flex;
            gap: 1rem;
            align-items: center;
        }

        .user-welcome {
            color: var(--white);
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .cart-icon, .wishlist-icon {
            position: relative;
            cursor: pointer;
        }

        .cart-count, .wishlist-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: var(--prophetic-gold);
            color: var(--prophetic-blue);
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
            font-weight: bold;
        }

        .auth-buttons {
            display: flex;
            gap: 0.5rem;
        }

        .btn {
            padding: 0.5rem 1rem;
            border-radius: 5px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            border: none;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 0.9rem;
        }

        .btn-outline {
            background: transparent;
            border: 1px solid var(--white);
            color: var(--white);
        }

        .btn-primary {
            background: var(--prophetic-gold);
            color: var(--prophetic-blue);
        }

        .btn-primary:hover {
            background: #e6b800;
        }

        .btn-outline:hover {
            background: rgba(255,255,255,0.1);
        }

        .btn-danger {
            background: var(--error);
            color: var(--white);
        }

        .menu-toggle {
            display: none;
            background: none;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Search Container */
        .search-container {
            margin: 1rem 0;
            position: relative;
        }

        .search-results {
            position: absolute;
            top: 100%;
            left: 0;
            right: 0;
            background: white;
            border: 1px solid #e5e7eb;
            border-radius: 5px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            max-height: 300px;
            overflow-y: auto;
            z-index: 100;
            display: none;
        }

        .search-result-item {
            padding: 0.75rem 1rem;
            border-bottom: 1px solid #e5e7eb;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }

        .search-result-item:hover {
            background: var(--light-gray);
        }

        .search-result-icon {
            font-size: 1.2rem;
            width: 30px;
            text-align: center;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(30, 58, 138, 0.9), rgba(220, 38, 38, 0.9)), url('https://images.unsplash.com/photo-1532629345422-7515f3d16bb6?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            color: var(--white);
            text-align: center;
            padding: 6rem 2rem;
            position: relative;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            font-style: italic;
        }

        /* Sections */
        section {
            max-width: 1200px;
            margin: 0 auto;
            padding: 3rem 1.5rem;
        }

        section h2 {
            color: var(--prophetic-blue);
            font-size: 2.2rem;
            margin-bottom: 2rem;
            text-align: center;
            position: relative;
        }

        section h2:after {
            content: '';
            display: block;
            width: 100px;
            height: 4px;
            background: var(--prophetic-gold);
            margin: 0.5rem auto;
            border-radius: 2px;
        }

        /* Products Grid */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .product-card {
            background: var(--white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            display: flex;
            flex-direction: column;
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
        }

        .product-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, var(--prophetic-blue), var(--prophetic-red));
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 3rem;
        }

        .wishlist-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background: rgba(255,255,255,0.9);
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-size: 1.2rem;
            color: #ccc;
            transition: all 0.3s;
        }

        .wishlist-btn.active {
            color: var(--prophetic-red);
        }

        .wishlist-btn:hover {
            transform: scale(1.1);
        }

        .product-content {
            padding: 1.5rem;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .product-content h3 {
            color: var(--prophetic-blue);
            margin-bottom: 0.5rem;
        }

        .product-content p {
            margin-bottom: 1rem;
            color: var(--dark-gray);
            flex-grow: 1;
        }

        .product-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: auto;
        }

        .price {
            font-size: 1.5rem;
            color: var(--prophetic-red);
            font-weight: bold;
        }

        .in-stock {
            color: var(--success);
            font-size: 0.9rem;
            font-weight: bold;
        }

        .out-of-stock {
            color: var(--error);
            font-size: 0.9rem;
            font-weight: bold;
        }

        /* Cart Sidebar */
        .cart-sidebar, .wishlist-sidebar {
            position: fixed;
            top: 0;
            right: -400px;
            width: 400px;
            height: 100vh;
            background: var(--white);
            box-shadow: -5px 0 15px rgba(0,0,0,0.1);
            transition: right 0.3s ease;
            z-index: 1100;
            display: flex;
            flex-direction: column;
        }

        .cart-sidebar.active, .wishlist-sidebar.active {
            right: 0;
        }

        .cart-header, .wishlist-header {
            padding: 1.5rem;
            border-bottom: 1px solid #e5e7eb;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: var(--prophetic-blue);
            color: var(--white);
        }

        .cart-header h3, .wishlist-header h3 {
            margin: 0;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .close-cart, .close-wishlist {
            background: none;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
        }

        .cart-items, .wishlist-items {
            flex-grow: 1;
            overflow-y: auto;
            padding: 1rem;
        }

        .cart-item, .wishlist-item {
            display: flex;
            gap: 1rem;
            padding: 1rem 0;
            border-bottom: 1px solid #e5e7eb;
        }

        .cart-item-image, .wishlist-item-image {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, var(--prophetic-blue), var(--prophetic-red));
            border-radius: 5px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 1.5rem;
        }

        .cart-item-details, .wishlist-item-details {
            flex-grow: 1;
        }

        .cart-item-details h4, .wishlist-item-details h4 {
            color: var(--prophetic-blue);
            margin-bottom: 0.5rem;
        }

        .cart-item-controls {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-top: 0.5rem;
        }

        .quantity-btn {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            border: 1px solid #d1d5db;
            background: var(--white);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
        }

        .quantity {
            margin: 0 0.5rem;
            font-weight: bold;
        }

        .remove-item {
            color: var(--prophetic-red);
            background: none;
            border: none;
            cursor: pointer;
            margin-left: auto;
        }

        .cart-footer, .wishlist-footer {
            padding: 1.5rem;
            border-top: 1px solid #e5e5e5;
            background: var(--light-gray);
        }

        .cart-total {
            display: flex;
            justify-content: space-between;
            font-size: 1.2rem;
            font-weight: bold;
            margin-bottom: 1rem;
        }

        .checkout-btn {
            width: 100%;
            padding: 1rem;
            background: var(--prophetic-red);
            color: var(--white);
            border: none;
            border-radius: 5px;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
        }

        .checkout-btn:hover {
            background: #b91c1c;
        }

        .empty-cart, .empty-wishlist {
            text-align: center;
            padding: 2rem;
            color: #6b7280;
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 1200;
            align-items: center;
            justify-content: center;
            padding: 1rem;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 10px;
            max-width: 500px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            position: relative;
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
            border-bottom: 1px solid #e5e7eb;
            padding-bottom: 1rem;
        }

        .modal-header h3 {
            color: var(--prophetic-blue);
            margin: 0;
        }

        .close-modal {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--dark-gray);
        }

        /* Auth Tabs */
        .auth-tabs {
            display: flex;
            margin-bottom: 1.5rem;
            border-bottom: 1px solid #e5e7eb;
            overflow-x: auto;
        }

        .auth-tab {
            padding: 0.75rem 1.5rem;
            background: none;
            border: none;
            cursor: pointer;
            font-weight: 600;
            color: var(--dark-gray);
            border-bottom: 3px solid transparent;
            white-space: nowrap;
        }

        .auth-tab.active {
            color: var(--prophetic-blue);
            border-bottom: 3px solid var(--prophetic-blue);
        }

        .auth-form {
            display: none;
        }

        .auth-form.active {
            display: block;
        }

        /* Form Styles */
        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--prophetic-blue);
            font-weight: bold;
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #d1d5db;
            border-radius: 5px;
            font-family: inherit;
        }

        .form-group textarea {
            min-height: 120px;
            resize: vertical;
        }

        .form-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 1.5rem;
        }

        .forgot-password {
            color: var(--prophetic-blue);
            text-decoration: none;
            font-size: 0.9rem;
        }

        .forgot-password:hover {
            text-decoration: underline;
        }

        /* User Profile */
        .profile-section {
            background: var(--light-gray);
            padding: 2rem;
            border-radius: 10px;
            margin-bottom: 2rem;
        }

        .profile-header {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .profile-avatar {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, var(--prophetic-blue), var(--prophetic-red));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 2rem;
        }

        .profile-info h3 {
            color: var(--prophetic-blue);
            margin-bottom: 0.5rem;
        }

        .profile-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .stat-card {
            background: var(--white);
            padding: 1.5rem;
            border-radius: 8px;
            text-align: center;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .stat-number {
            font-size: 2rem;
            font-weight: bold;
            color: var(--prophetic-blue);
            display: block;
        }

        .stat-label {
            color: var(--dark-gray);
            font-size: 0.9rem;
        }

        /* Order History */
        .order-history {
            margin-top: 2rem;
        }

        .order-card {
            background: var(--white);
            border: 1px solid #e5e7eb;
            border-radius: 8px;
            padding: 1.5rem;
            margin-bottom: 1rem;
        }

        .order-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
        }

        .order-id {
            font-weight: bold;
            color: var(--prophetic-blue);
        }

        .order-date {
            color: #6b7280;
            font-size: 0.9rem;
        }

        .order-status {
            padding: 0.25rem 0.75rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
        }

        .status-completed {
            background: var(--success);
            color: white;
        }

        .status-pending {
            background: var(--warning);
            color: white;
        }

        /* Cookie Consent */
        #cookieConsent {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background: #333;
            color: white;
            padding: 1rem;
            z-index: 2000;
            display: none;
        }

        .cookie-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 1rem;
        }

        /* Footer */
        footer {
            background: var(--prophetic-blue);
            color: var(--white);
            padding: 3rem 1.5rem 1.5rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
            color: var(--prophetic-gold);
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 0.5rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .footer-section a {
            color: var(--white);
            text-decoration: none;
        }

        .footer-section a:hover {
            text-decoration: underline;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            transition: background 0.3s;
        }

        .social-links a:hover {
            background: rgba(255,255,255,0.2);
        }

        .footer-bottom {
            max-width: 1200px;
            margin: 0 auto;
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        /* Utility Classes */
        .hidden {
            display: none !important;
        }

        .text-center {
            text-align: center;
        }

        .alt-bg {
            background-color: var(--light-gray);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }

            .nav-container {
                flex-direction: column;
                align-items: flex-start;
                width: 100%;
                position: absolute;
                top: 100%;
                left: 0;
                background: var(--prophetic-blue);
                padding: 1rem;
                display: none;
            }

            .nav-container.active {
                display: flex;
            }

            .nav-links {
                flex-direction: column;
                width: 100%;
                gap: 1rem;
            }

            .user-actions {
                flex-direction: column;
                width: 100%;
                gap: 0.5rem;
            }

            .hero h2 {
                font-size: 2rem;
            }

            .cart-sidebar, .wishlist-sidebar {
                width: 100%;
                right: -100%;
            }

            .cookie-content {
                flex-direction: column;
                text-align: center;
            }

            .modal-content {
                padding: 1.5rem;
            }

            .profile-header {
                flex-direction: column;
                text-align: center;
            }

            .form-footer {
                flex-direction: column;
                gap: 1rem;
                align-items: stretch;
            }
        }

        /* Loading Spinner */
        .spinner {
            border: 4px solid #f3f3f3;
            border-top: 4px solid var(--prophetic-blue);
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 2s linear infinite;
            margin: 0 auto;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        @keyframes slideIn {
            from { transform: translateX(100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }
    </style>
</head>
<body>
    <!-- Cookie Consent Banner -->
    <div id="cookieConsent">
        <div class="cookie-content">
            <p>We use cookies to enhance your experience. By continuing to visit this site you agree to our use of cookies.</p>
            <button onclick="acceptCookies()" class="btn btn-primary">Accept</button>
        </div>
    </div>

    <!-- Header -->
    <header>
        <nav>
            <div class="logo">
                <h1><i class="fas fa-cross"></i> The Definitive Word</h1>
                <p>Your Destiny Has Been Written</p>
            </div>
            
            <button class="menu-toggle" onclick="toggleMenu()">
                <i class="fas fa-bars"></i>
            </button>
            
            <div class="nav-container" id="navContainer">
                <ul class="nav-links">
                    <li><a href="#home"><i class="fas fa-home"></i> Home</a></li>
                    <li><a href="#products"><i class="fas fa-book"></i> Products</a></li>
                    <li><a href="#coaching"><i class="fas fa-hands-helping"></i> Coaching</a></li>
                    <li><a href="#blog"><i class="fas fa-blog"></i> Blog</a></li>
                    <li><a href="#workshops"><i class="fas fa-users"></i> Workshops</a></li>
                    <li><a href="#ministry"><i class="fas fa-church"></i> Ministry</a></li>
                    <li><a href="#contact"><i class="fas fa-envelope"></i> Contact</a></li>
                </ul>
                
                <div class="user-actions">
                    <div class="wishlist-icon" onclick="toggleWishlist()">
                        <i class="fas fa-heart"></i>
                        <span class="wishlist-count">0</span>
                    </div>
                    <div class="cart-icon" onclick="toggleCart()">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count">0</span>
                    </div>
                    
                    <div class="auth-buttons" id="authButtons">
                        <!-- Will be populated by JavaScript -->
                    </div>
                </div>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h2>Welcome to The Definitive Word</h2>
            <p>Your Destiny Has Been Written</p>
            <p>Discover God's plan for your life through prophetic teaching, life coaching, and transformative resources</p>
            <button class="btn btn-primary" onclick="scrollToSection('products')">
                <i class="fas fa-shopping-bag"></i> Explore Our Resources
            </button>
        </div>
    </section>

    <!-- User Profile Section (Hidden by default) -->
    <section id="userProfile" class="hidden">
        <h2>My Account</h2>
        <div class="profile-section">
            <div class="profile-header">
                <div class="profile-avatar">
                    <i class="fas fa-user"></i>
                </div>
                <div class="profile-info">
                    <h3 id="userProfileName">Loading...</h3>
                    <p id="userProfileEmail">Loading...</p>
                    <p>Member since <span id="userJoinDate">2025</span></p>
                </div>
            </div>
            
            <div class="profile-stats">
                <div class="stat-card">
                    <span class="stat-number" id="ordersCount">0</span>
                    <span class="stat-label">Orders</span>
                </div>
                <div class="stat-card">
                    <span class="stat-number" id="wishlistCount">0</span>
                    <span class="stat-label">Wishlist Items</span>
                </div>
                <div class="stat-card">
                    <span class="stat-number" id="coachingSessions">0</span>
                    <span class="stat-label">Coaching Sessions</span>
                </div>
            </div>

            <div class="user-actions">
                <button class="btn btn-primary" onclick="openEditProfileModal()">
                    <i class="fas fa-edit"></i> Edit Profile
                </button>
                <button class="btn btn-outline" onclick="openChangePasswordModal()">
                    <i class="fas fa-key"></i> Change Password
                </button>
                <button class="btn btn-danger" onclick="logout()">
                    <i class="fas fa-sign-out-alt"></i> Logout
                </button>
            </div>
        </div>

        <div class="order-history">
            <h3>Order History</h3>
            <div id="orderHistory">
                <p>No orders yet. <a href="#products" onclick="scrollToSection('products')">Start shopping!</a></p>
            </div>
        </div>
    </section>

    <!-- Search Section -->
    <section class="alt-bg">
        <div class="search-container">
            <input type="text" id="searchInput" placeholder="Search products, blog posts, workshops..." 
                   style="width: 100%; padding: 0.8rem; border: 1px solid #d1d5db; border-radius: 5px;">
            <div class="search-results" id="searchResults"></div>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products">
        <h2>Featured Products</h2>
        <p class="text-center" style="max-width: 800px; margin: 0 auto 2rem;">
            Dive deep into prophetic wisdom and biblical teaching with our collection of transformative resources.
        </p>
        
        <div class="products-grid" id="productsGrid">
            <!-- Product cards will be dynamically generated -->
        </div>
    </section>

    <!-- Coaching Section -->
    <section id="coaching" class="alt-bg">
        <h2>Life Coaching</h2>
        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; align-items: center;">
            <div>
                <h3 style="color: var(--prophetic-blue); margin-bottom: 1rem;">Transform Your Life Through Prophetic Coaching</h3>
                <p style="margin-bottom: 1.5rem;">Our life coaching program combines biblical principles with practical strategies to help you:</p>
                <ul style="margin-left: 1.5rem; margin-bottom: 2rem;">
                    <li style="margin-bottom: 0.8rem;">Discover your divine purpose and calling</li>
                    <li style="margin-bottom: 0.8rem;">Overcome obstacles and limiting beliefs</li>
                    <li style="margin-bottom: 0.8rem;">Develop spiritual disciplines and growth</li>
                    <li style="margin-bottom: 0.8rem;">Create actionable plans for your goals</li>
                    <li style="margin-bottom: 0.8rem;">Walk in the fullness of your destiny</li>
                </ul>
                <button class="btn btn-primary" onclick="addToCart('Life Coaching Session', 0, 'coaching')">
                    <i class="fas fa-calendar-check"></i> Book a Session
                </button>
            </div>
            <div>
                <div style="background: linear-gradient(135deg, var(--prophetic-blue), var(--prophetic-red)); height: 400px; border-radius: 10px; display: flex; align-items: center; justify-content: center; color: white; font-size: 4rem;">
                    <i class="fas fa-bullseye"></i>
                </div>
            </div>
        </div>
    </section>

    <!-- Blog Section -->
    <section id="blog">
        <h2>Latest from the Blog</h2>
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; margin-top: 2rem;" id="blogContainer">
            <!-- Blog posts will be dynamically generated -->
        </div>
    </section>

    <!-- Workshops Section -->
    <section id="workshops" class="alt-bg">
        <h2>Upcoming Workshops</h2>
        <div style="display: grid; gap: 2rem; margin-top: 2rem;" id="workshopsContainer">
            <!-- Workshop cards will be dynamically generated -->
        </div>
    </section>

    <!-- Ministry Section -->
    <section id="ministry">
        <h2>Our Ministry</h2>
        <div style="max-width: 800px; margin: 0 auto; text-align: center;">
            <p style="font-size: 1.2rem; margin-bottom: 2rem;">
                The Definitive Word Ministry is dedicated to helping believers understand that their destiny has already been written by God. Through prophetic teaching, life coaching, and biblical resources, we equip people to walk confidently in their divine calling.
            </p>
            
            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 2rem; margin: 3rem 0;">
                <div>
                    <div style="font-size: 3rem; color: var(--prophetic-blue);">
                        <i class="fas fa-book-open"></i>
                    </div>
                    <h3 style="color: var(--prophetic-blue); margin: 1rem 0;">Teaching</h3>
                    <p>Biblical and prophetic instruction</p>
                </div>
                <div>
                    <div style="font-size: 3rem; color: var(--prophetic-red);">
                        <i class="fas fa-pray"></i>
                    </div>
                    <h3 style="color: var(--prophetic-red); margin: 1rem 0;">Prayer</h3>
                    <p>Intercessory and prophetic prayer</p>
                </div>
                <div>
                    <div style="font-size: 3rem; color: var(--prophetic-blue);">
                        <i class="fas fa-hands-helping"></i>
                    </div>
                    <h3 style="color: var(--prophetic-blue); margin: 1rem 0;">Coaching</h3>
                    <p>Personal transformation guidance</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="alt-bg">
        <h2>Get In Touch</h2>
        <div style="max-width: 600px; margin: 2rem auto; background: var(--white); padding: 2rem; border-radius: 10px;">
            <form id="contactForm">
                <div class="form-group">
                    <label for="name">Name</label>
                    <input type="text" id="name" name="name" required>
                </div>
                <div class="form-group">
                    <label for="email">Email</label>
                    <input type="email" id="email" name="email" required>
                </div>
                <div class="form-group">
                    <label for="subject">Subject</label>
                    <select id="subject" name="subject" required>
                        <option value="">Select a topic...</option>
                        <option value="products">Products</option>
                        <option value="coaching">Life Coaching</option>
                        <option value="workshops">Workshops</option>
                        <option value="ministry">Ministry Inquiry</option>
                        <option value="other">Other</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="message">Message</label>
                    <textarea id="message" name="message" required></textarea>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">
                    <i class="fas fa-paper-plane"></i> Send Message
                </button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>The Definitive Word</h3>
                <p>Your Destiny Has Been Written. We are dedicated to helping you discover and walk in your God-given purpose through prophetic teaching and life coaching.</p>
                <div class="social-links">
                    <a href="#" onclick="shareOnFacebook()"><i class="fab fa-facebook-f"></i></a>
                    <a href="#" onclick="shareOnTwitter()"><i class="fab fa-twitter"></i></a>
                    <a href="#" onclick="shareOnLinkedIn()"><i class="fab fa-linkedin"></i></a>
                    <a href="#" onclick="shareOnWhatsApp()"><i class="fab fa-whatsapp"></i></a>
                </div>
            </div>
            
            <div class="footer-section">
                <h3>Quick Links</h3>
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#products">Products</a></li>
                    <li><a href="#coaching">Coaching</a></li>
                    <li><a href="#blog">Blog</a></li>
                    <li><a href="#workshops">Workshops</a></li>
                </ul>
            </div>
            
            <div class="footer-section">
                <h3>Contact Us</h3>
                <ul>
                    <li><i class="fas fa-map-marker-alt"></i> Cape Town, South Africa</li>
                    <li><i class="fas fa-phone"></i> +27 21 123 4567</li>
                    <li><i class="fas fa-envelope"></i> info@definitiveword.org</li>
                </ul>
            </div>
        </div>
        
        <div class="footer-bottom">
            <p>&copy; 2025 The Definitive Word Ministry. Your Destiny Has Been Written.</p>
            <p style="margin-top: 0.5rem; font-size: 0.9rem;">Walking in prophetic purpose since 2025</p>
        </div>
    </footer>

    <!-- Shopping Cart Sidebar -->
    <div class="cart-sidebar" id="cartSidebar">
        <div class="cart-header">
            <h3><i class="fas fa-shopping-cart"></i> Your Cart</h3>
            <button class="close-cart" onclick="toggleCart()">
                <i class="fas fa-times"></i>
            </button>
        </div>
        <div class="cart-items" id="cartItems">
            <!-- Cart items will be dynamically added here -->
        </div>
        <div class="cart-footer">
            <div class="cart-total">
                <span>Total:</span>
                <span id="cartTotal">R 0.00</span>
            </div>
            <button class="checkout-btn" id="checkoutBtn" onclick="checkout()">
                <i class="fas fa-lock"></i> Proceed to Checkout
            </button>
        </div>
    </div>

    <!-- Wishlist Sidebar -->
    <div class="wishlist-sidebar" id="wishlistSidebar">
        <div class="wishlist-header">
            <h3><i class="fas fa-heart"></i> Your Wishlist</h3>
            <button class="close-wishlist" onclick="toggleWishlist()">
                <i class="fas fa-times"></i>
            </button>
        </div>
        <div class="wishlist-items" id="wishlistItems">
            <!-- Wishlist items will be dynamically added here -->
        </div>
        <div class="wishlist-footer">
            <button class="checkout-btn" onclick="toggleWishlist()">
                Continue Shopping
            </button>
        </div>
    </div>

    <!-- Auth Modal -->
    <div class="modal" id="authModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 id="authModalTitle">Login to Your Account</h3>
                <button class="close-modal" onclick="closeAuthModal()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <div class="auth-tabs">
                <button class="auth-tab active" onclick="switchAuthTab('login')">Login</button>
                <button class="auth-tab" onclick="switchAuthTab('register')">Register</button>
            </div>
            
            <form id="loginForm" class="auth-form active">
                <div class="form-group">
                    <label for="loginEmail">Email</label>
                    <input type="email" id="loginEmail" required>
                </div>
                <div class="form-group">
                    <label for="loginPassword">Password</label>
                    <input type="password" id="loginPassword" required>
                </div>
                <div class="form-footer">
                    <a href="#" class="forgot-password" onclick="openForgotPasswordModal(); return false;">Forgot Password?</a>
                    <button type="submit" class="btn btn-primary">Login</button>
                </div>
            </form>
            
            <form id="registerForm" class="auth-form">
                <div class="form-group">
                    <label for="registerName">Full Name</label>
                    <input type="text" id="registerName" required>
                </div>
                <div class="form-group">
                    <label for="registerEmail">Email</label>
                    <input type="email" id="registerEmail" required>
                </div>
                <div class="form-group">
                    <label for="registerPassword">Password</label>
                    <input type="password" id="registerPassword" required>
                </div>
                <div class="form-group">
                    <label for="registerConfirmPassword">Confirm Password</label>
                    <input type="password" id="registerConfirmPassword" required>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%; margin-top: 1rem;">Create Account</button>
            </form>
        </div>
    </div>

    <!-- Forgot Password Modal -->
    <div class="modal" id="forgotPasswordModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Reset Your Password</h3>
                <button class="close-modal" onclick="closeForgotPasswordModal()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <form id="forgotPasswordForm">
                <div class="form-group">
                    <label for="resetEmail">Email Address</label>
                    <input type="email" id="resetEmail" required placeholder="Enter your email address">
                </div>
                <p style="margin-bottom: 1rem; color: #6b7280; font-size: 0.9rem;">
                    We'll send you a link to reset your password.
                </p>
                <button type="submit" class="btn btn-primary" style="width: 100%;">
                    Send Reset Link
                </button>
            </form>
            
            <div style="text-align: center; margin-top: 1rem;">
                <a href="#" onclick="closeForgotPasswordModal(); openAuthModal(); return false;" style="color: var(--prophetic-blue); text-decoration: none;">
                    Back to Login
                </a>
            </div>
        </div>
    </div>

    <!-- Change Password Modal -->
    <div class="modal" id="changePasswordModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Change Password</h3>
                <button class="close-modal" onclick="closeChangePasswordModal()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <form id="changePasswordForm">
                <div class="form-group">
                    <label for="currentPassword">Current Password</label>
                    <input type="password" id="currentPassword" required>
                </div>
                <div class="form-group">
                    <label for="newPassword">New Password</label>
                    <input type="password" id="newPassword" required>
                </div>
                <div class="form-group">
                    <label for="confirmNewPassword">Confirm New Password</label>
                    <input type="password" id="confirmNewPassword" required>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">
                    Update Password
                </button>
            </form>
        </div>
    </div>

    <!-- Edit Profile Modal -->
    <div class="modal" id="editProfileModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Edit Profile</h3>
                <button class="close-modal" onclick="closeEditProfileModal()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <form id="editProfileForm">
                <div class="form-group">
                    <label for="editName">Full Name</label>
                    <input type="text" id="editName" required>
                </div>
                <div class="form-group">
                    <label for="editEmail">Email Address</label>
                    <input type="email" id="editEmail" required>
                </div>
                <div class="form-group">
                    <label for="editPhone">Phone Number</label>
                    <input type="tel" id="editPhone" placeholder="Optional">
                </div>
                <div class="form-group">
                    <label for="editBio">Bio</label>
                    <textarea id="editBio" placeholder="Tell us about yourself..." rows="4"></textarea>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">
                    Save Changes
                </button>
            </form>
        </div>
    </div>

    <!-- Payment Modal -->
    <div class="modal" id="paymentModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Complete Your Purchase</h3>
                <button class="close-modal" onclick="closePaymentModal()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <div id="paymentContent">
                <!-- Payment content will be dynamically added here -->
            </div>
        </div>
    </div>

    <script>
        // Application State
        const state = {
            user: null,
            cart: [],
            wishlist: [],
            orders: [],
            users: [
                {
                    id: 1,
                    name: "Admin User",
                    email: "admin@definitiveword.org",
                    password: "admin123",
                    role: "admin",
                    joinDate: "2025-01-01",
                    phone: "+27 21 123 4567",
                    bio: "Site administrator and ministry leader."
                }
            ],
            products: [
                {
                    id: 1,
                    name: "Unveiling Your Destiny",
                    description: "A comprehensive guide to discovering and walking in your God-given purpose.",
                    price: 299.99,
                    category: "ebook",
                    image: "📖",
                    inventory: 100,
                    sku: "EBK-001"
                },
                {
                    id: 2,
                    name: "Prophetic Insights",
                    description: "Understanding the prophetic voice in the modern church and your personal life.",
                    price: 349.99,
                    category: "ebook",
                    image: "🕊️",
                    inventory: 50,
                    sku: "EBK-002"
                },
                {
                    id: 3,
                    name: "Destiny Declarations",
                    description: "Powerful declarations to speak over your life and activate your destiny.",
                    price: 199.99,
                    category: "ebook",
                    image: "🗣️",
                    inventory: 75,
                    sku: "EBK-003"
                },
                {
                    id: 4,
                    name: "The Prophetic Journey",
                    description: "A 30-day devotional to deepen your prophetic understanding and walk.",
                    price: 249.99,
                    category: "ebook",
                    image: "🛤️",
                    inventory: 60,
                    sku: "EBK-004"
                }
            ],
            blogPosts: [
                {
                    id: 1,
                    title: "Walking in Your Prophetic Purpose",
                    description: "Discovering how to align your daily life with the prophetic words spoken over you...",
                    date: "2025-11-20",
                    content: "Full blog post content would go here..."
                },
                {
                    id: 2,
                    title: "Understanding God's Timing",
                    description: "Learning to trust in divine timing when pursuing your God-given destiny...",
                    date: "2025-11-15",
                    content: "Full blog post content would go here..."
                },
                {
                    id: 3,
                    title: "The Power of Prophetic Declaration",
                    description: "How speaking God's promises can activate your destiny and transform your life...",
                    date: "2025-11-10",
                    content: "Full blog post content would go here..."
                }
            ],
            workshops: [
                {
                    id: 1,
                    title: "Prophetic Activation Workshop",
                    description: "A powerful one-day intensive designed to activate and strengthen your prophetic gifting.",
                    date: "2025-12-15",
                    price: 499.99,
                    location: "Virtual (Zoom)",
                    time: "9:00 AM - 4:00 PM",
                    inventory: 20
                },
                {
                    id: 2,
                    title: "Destiny Discovery Intensive",
                    description: "A weekend workshop focused on uncovering your unique purpose and calling.",
                    date: "2025-12-20",
                    price: 799.99,
                    location: "Cape Town, South Africa",
                    time: "9:00 AM - 5:00 PM",
                    inventory: 15
                },
                {
                    id: 3,
                    title: "Prophetic Ministry Training",
                    description: "Advanced training for those called to prophetic ministry and leadership.",
                    date: "2026-01-10",
                    price: 999.99,
                    location: "Virtual (Zoom)",
                    time: "10:00 AM - 3:00 PM",
                    inventory: 25
                }
            ]
        };

        // DOM Elements
        const elements = {
            cartSidebar: document.getElementById('cartSidebar'),
            wishlistSidebar: document.getElementById('wishlistSidebar'),
            cartItems: document.getElementById('cartItems'),
            wishlistItems: document.getElementById('wishlistItems'),
            cartTotal: document.getElementById('cartTotal'),
            cartCount: document.querySelector('.cart-count'),
            wishlistCount: document.querySelector('.wishlist-count'),
            authModal: document.getElementById('authModal'),
            forgotPasswordModal: document.getElementById('forgotPasswordModal'),
            changePasswordModal: document.getElementById('changePasswordModal'),
            editProfileModal: document.getElementById('editProfileModal'),
            paymentModal: document.getElementById('paymentModal'),
            authButtons: document.getElementById('authButtons'),
            userProfile: document.getElementById('userProfile'),
            productsGrid: document.getElementById('productsGrid'),
            blogContainer: document.getElementById('blogContainer'),
            workshopsContainer: document.getElementById('workshopsContainer'),
            navContainer: document.getElementById('navContainer'),
            searchInput: document.getElementById('searchInput'),
            searchResults: document.getElementById('searchResults')
        };

        // Initialize the application
        function init() {
            checkLoginStatus();
            renderProducts();
            renderBlogPosts();
            renderWorkshops();
            updateCartUI();
            updateWishlistUI();
            checkCookieConsent();
            
            // Set up event listeners
            document.getElementById('loginForm').addEventListener('submit', handleLogin);
            document.getElementById('registerForm').addEventListener('submit', handleRegister);
            document.getElementById('forgotPasswordForm').addEventListener('submit', handleForgotPassword);
            document.getElementById('changePasswordForm').addEventListener('submit', handleChangePassword);
            document.getElementById('editProfileForm').addEventListener('submit', handleEditProfile);
            document.getElementById('contactForm').addEventListener('submit', handleContact);
            
            // Search functionality
            elements.searchInput.addEventListener('input', handleSearch);
            document.addEventListener('click', function(e) {
                if (!elements.searchResults.contains(e.target) && e.target !== elements.searchInput) {
                    elements.searchResults.style.display = 'none';
                }
            });
        }

        // Authentication Functions
        function checkLoginStatus() {
            const savedUser = localStorage.getItem('currentUser');
            if (savedUser) {
                state.user = JSON.parse(savedUser);
                updateAuthUI();
            } else {
                showLoginButtons();
            }
        }

        function updateAuthUI() {
            if (state.user) {
                elements.authButtons.innerHTML = `
                    <div class="user-welcome">
                        <i class="fas fa-user"></i>
                        <span>Hello, ${state.user.name}</span>
                    </div>
                    <button class="btn btn-outline" onclick="showUserProfile()">
                        <i class="fas fa-user-circle"></i> My Account
                    </button>
                    <button class="btn btn-outline" onclick="logout()">
                        <i class="fas fa-sign-out-alt"></i> Logout
                    </button>
                `;
            } else {
                showLoginButtons();
            }
        }

        function showLoginButtons() {
            elements.authButtons.innerHTML = `
                <button class="btn btn-outline" onclick="openAuthModal()">
                    <i class="fas fa-user"></i> Login
                </button>
                <button class="btn btn-primary" onclick="openAuthModal('register')">
                    <i class="fas fa-user-plus"></i> Sign Up
                </button>
            `;
        }

        function handleLogin(e) {
            e.preventDefault();
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;
            
            // Find user
            const user = state.users.find(u => u.email === email && u.password === password);
            
            if (user) {
                // Remove password from user object before storing
                const { password: _, ...userWithoutPassword } = user;
                state.user = userWithoutPassword;
                localStorage.setItem('currentUser', JSON.stringify(state.user));
                
                closeAuthModal();
                updateAuthUI();
                showNotification('Login successful!', 'success');
            } else {
                showNotification('Invalid email or password', 'error');
            }
        }

        function handleRegister(e) {
            e.preventDefault();
            const name = document.getElementById('registerName').value;
            const email = document.getElementById('registerEmail').value;
            const password = document.getElementById('registerPassword').value;
            const confirmPassword = document.getElementById('registerConfirmPassword').value;
            
            if (password !== confirmPassword) {
                showNotification('Passwords do not match', 'error');
                return;
            }
            
            // Check if user already exists
            if (state.users.find(u => u.email === email)) {
                showNotification('User with this email already exists', 'error');
                return;
            }
            
            // Create new user
            const newUser = {
                id: Date.now(),
                name,
                email,
                password,
                role: 'customer',
                joinDate: new Date().toISOString().split('T')[0],
                phone: '',
                bio: ''
            };
            
            state.users.push(newUser);
            
            // Remove password from user object before storing
            const { password: _, ...userWithoutPassword } = newUser;
            state.user = userWithoutPassword;
            localStorage.setItem('currentUser', JSON.stringify(state.user));
            
            closeAuthModal();
            updateAuthUI();
            showNotification('Account created successfully!', 'success');
        }

        function handleForgotPassword(e) {
            e.preventDefault();
            const email = document.getElementById('resetEmail').value;
            
            // Check if user exists
            const user = state.users.find(u => u.email === email);
            
            if (user) {
                closeForgotPasswordModal();
                showNotification('Password reset link has been sent to your email', 'success');
            } else {
                showNotification('No account found with this email', 'error');
            }
        }

        function handleChangePassword(e) {
            e.preventDefault();
            const currentPassword = document.getElementById('currentPassword').value;
            const newPassword = document.getElementById('newPassword').value;
            const confirmNewPassword = document.getElementById('confirmNewPassword').value;
            
            if (newPassword !== confirmNewPassword) {
                showNotification('New passwords do not match', 'error');
                return;
            }
            
            // Find user and update password
            const userIndex = state.users.findIndex(u => u.email === state.user.email);
            if (userIndex !== -1 && state.users[userIndex].password === currentPassword) {
                state.users[userIndex].password = newPassword;
                closeChangePasswordModal();
                showNotification('Password updated successfully', 'success');
            } else {
                showNotification('Current password is incorrect', 'error');
            }
        }

        function handleEditProfile(e) {
            e.preventDefault();
            const name = document.getElementById('editName').value;
            const email = document.getElementById('editEmail').value;
            const phone = document.getElementById('editPhone').value;
            const bio = document.getElementById('editBio').value;
            
            // Update user in state
            const userIndex = state.users.findIndex(u => u.email === state.user.email);
            if (userIndex !== -1) {
                state.users[userIndex].name = name;
                state.users[userIndex].email = email;
                state.users[userIndex].phone = phone;
                state.users[userIndex].bio = bio;
                
                // Update current user
                state.user.name = name;
                state.user.email = email;
                state.user.phone = phone;
                state.user.bio = bio;
                
                localStorage.setItem('currentUser', JSON.stringify(state.user));
                
                closeEditProfileModal();
                updateAuthUI();
                updateUserProfile();
                showNotification('Profile updated successfully', 'success');
            }
        }

        function logout() {
            state.user = null;
            localStorage.removeItem('currentUser');
            updateAuthUI();
            hideUserProfile();
            showNotification('Logged out successfully', 'success');
        }

        // User Profile Functions
        function showUserProfile() {
            // Hide all sections
            document.querySelectorAll('section').forEach(section => {
                section.classList.add('hidden');
            });
            
            // Show user profile section
            elements.userProfile.classList.remove('hidden');
            updateUserProfile();
            scrollToSection('userProfile');
        }

        function hideUserProfile() {
            elements.userProfile.classList.add('hidden');
            document.getElementById('home').classList.remove('hidden');
        }

        function updateUserProfile() {
            if (!state.user) return;
            
            document.getElementById('userProfileName').textContent = state.user.name;
            document.getElementById('userProfileEmail').textContent = state.user.email;
            document.getElementById('userJoinDate').textContent = state.user.joinDate;
            
            // Update stats
            const userOrders = state.orders.filter(order => order.customerEmail === state.user.email);
            document.getElementById('ordersCount').textContent = userOrders.length;
            document.getElementById('wishlistCount').textContent = state.wishlist.length;
            
            const coachingSessions = userOrders.filter(order => 
                order.items.some(item => item.category === 'coaching')
            ).length;
            document.getElementById('coachingSessions').textContent = coachingSessions;
            
            // Update order history
            const orderHistory = document.getElementById('orderHistory');
            if (userOrders.length === 0) {
                orderHistory.innerHTML = '<p>No orders yet. <a href="#products" onclick="scrollToSection(\'products\')">Start shopping!</a></p>';
            } else {
                orderHistory.innerHTML = userOrders.map(order => `
                    <div class="order-card">
                        <div class="order-header">
                            <div>
                                <span class="order-id">Order #${order.id}</span>
                                <div class="order-date">${new Date(order.date).toLocaleDateString()}</div>
                            </div>
                            <div class="order-status status-completed">Completed</div>
                        </div>
                        <div>
                            ${order.items.map(item => `
                                <div style="display: flex; justify-content: space-between; margin-bottom: 0.5rem;">
                                    <span>${item.name} x${item.quantity}</span>
                                    <span>R ${(item.price * item.quantity).toFixed(2)}</span>
                                </div>
                            `).join('')}
                            <hr style="margin: 0.5rem 0;">
                            <div style="display: flex; justify-content: space-between; font-weight: bold;">
                                <span>Total:</span>
                                <span>R ${order.total.toFixed(2)}</span>
                            </div>
                        </div>
                    </div>
                `).join('');
            }
            
            // Populate edit form
            document.getElementById('editName').value = state.user.name;
            document.getElementById('editEmail').value = state.user.email;
            document.getElementById('editPhone').value = state.user.phone || '';
            document.getElementById('editBio').value = state.user.bio || '';
        }

        // Modal Functions
        function openAuthModal(tab = 'login') {
            elements.authModal.classList.add('active');
            switchAuthTab(tab);
        }

        function closeAuthModal() {
            elements.authModal.classList.remove('active');
        }

        function openForgotPasswordModal() {
            closeAuthModal();
            elements.forgotPasswordModal.classList.add('active');
        }

        function closeForgotPasswordModal() {
            elements.forgotPasswordModal.classList.remove('active');
        }

        function openChangePasswordModal() {
            elements.changePasswordModal.classList.add('active');
        }

        function closeChangePasswordModal() {
            elements.changePasswordModal.classList.remove('active');
        }

        function openEditProfileModal() {
            elements.editProfileModal.classList.add('active');
        }

        function closeEditProfileModal() {
            elements.editProfileModal.classList.remove('active');
        }

        function switchAuthTab(tab) {
            document.querySelectorAll('.auth-tab').forEach(t => t.classList.remove('active'));
            document.querySelectorAll('.auth-form').forEach(f => f.classList.remove('active'));
            
            if (tab === 'login') {
                document.querySelector('.auth-tab:nth-child(1)').classList.add('active');
                document.getElementById('loginForm').classList.add('active');
                document.getElementById('authModalTitle').textContent = 'Login to Your Account';
            } else {
                document.querySelector('.auth-tab:nth-child(2)').classList.add('active');
                document.getElementById('registerForm').classList.add('active');
                document.getElementById('authModalTitle').textContent = 'Create New Account';
            }
        }

        // Product Functions
        function renderProducts() {
            if (!elements.productsGrid) return;
            
            elements.productsGrid.innerHTML = state.products.map(product => `
                <div class="product-card">
                    <div class="product-image">
                        ${product.image}
                    </div>
                    <button class="wishlist-btn" onclick="toggleWishlistItem(${product.id})">
                        <i class="fas fa-heart"></i>
                    </button>
                    <div class="product-content">
                        <h3>${product.name}</h3>
                        <p>${product.description}</p>
                        <div class="product-footer">
                            <div class="price">R ${product.price.toFixed(2)}</div>
                            <div class="${product.inventory > 0 ? 'in-stock' : 'out-of-stock'}">
                                ${product.inventory > 0 ? 'In Stock' : 'Out of Stock'}
                            </div>
                        </div>
                        <button class="btn btn-primary" style="width: 100%; margin-top: 1rem;" 
                                onclick="addToCart('${product.name}', ${product.price}, '${product.category}', ${product.id})"
                                ${product.inventory === 0 ? 'disabled' : ''}>
                            <i class="fas fa-cart-plus"></i> Add to Cart
                        </button>
                    </div>
                </div>
            `).join('');
        }

        function renderBlogPosts() {
            if (!elements.blogContainer) return;
            
            elements.blogContainer.innerHTML = state.blogPosts.map(post => `
                <div class="product-card">
                    <div class="product-image" style="background: linear-gradient(135deg, #10b981, #3b82f6);">
                        <i class="fas fa-blog"></i>
                    </div>
                    <div class="product-content">
                        <h3>${post.title}</h3>
                        <p>${post.description}</p>
                        <div class="product-footer">
                            <div style="color: #6b7280; font-size: 0.9rem;">
                                <i class="fas fa-calendar"></i> ${new Date(post.date).toLocaleDateString()}
                            </div>
                        </div>
                        <button class="btn btn-outline" style="width: 100%; margin-top: 1rem;">
                            <i class="fas fa-book-open"></i> Read More
                        </button>
                    </div>
                </div>
            `).join('');
        }

        function renderWorkshops() {
            if (!elements.workshopsContainer) return;
            
            elements.workshopsContainer.innerHTML = state.workshops.map(workshop => `
                <div class="product-card">
                    <div class="product-image" style="background: linear-gradient(135deg, #f59e0b, #dc2626);">
                        <i class="fas fa-users"></i>
                    </div>
                    <div class="product-content">
                        <h3>${workshop.title}</h3>
                        <p>${workshop.description}</p>
                        <div style="margin-bottom: 1rem;">
                            <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.5rem;">
                                <i class="fas fa-calendar"></i>
                                <span>${new Date(workshop.date).toLocaleDateString()}</span>
                            </div>
                            <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.5rem;">
                                <i class="fas fa-clock"></i>
                                <span>${workshop.time}</span>
                            </div>
                            <div style="display: flex; align-items: center; gap: 0.5rem;">
                                <i class="fas fa-map-marker-alt"></i>
                                <span>${workshop.location}</span>
                            </div>
                        </div>
                        <div class="product-footer">
                            <div class="price">R ${workshop.price.toFixed(2)}</div>
                            <div class="${workshop.inventory > 0 ? 'in-stock' : 'out-of-stock'}">
                                ${workshop.inventory > 0 ? `${workshop.inventory} spots left` : 'Sold Out'}
                            </div>
                        </div>
                        <button class="btn btn-primary" style="width: 100%; margin-top: 1rem;" 
                                onclick="addToCart('${workshop.title}', ${workshop.price}, 'workshop', ${workshop.id})"
                                ${workshop.inventory === 0 ? 'disabled' : ''}>
                            <i class="fas fa-ticket-alt"></i> Register Now
                        </button>
                    </div>
                </div>
            `).join('');
        }

        // Cart Functions
        function addToCart(name, price, category, id = null) {
            if (!state.user) {
                openAuthModal();
                showNotification('Please log in to add items to your cart', 'warning');
                return;
            }
            
            const existingItem = state.cart.find(item => item.name === name);
            
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                state.cart.push({
                    id: id || Date.now(),
                    name,
                    price,
                    category,
                    quantity: 1
                });
            }
            
            updateCartUI();
            showNotification(`${name} added to cart`, 'success');
        }

        function removeFromCart(itemId) {
            state.cart = state.cart.filter(item => item.id !== itemId);
            updateCartUI();
        }

        function updateCartQuantity(itemId, change) {
            const item = state.cart.find(item => item.id === itemId);
            if (item) {
                item.quantity += change;
                if (item.quantity <= 0) {
                    removeFromCart(itemId);
                } else {
                    updateCartUI();
                }
            }
        }

        function updateCartUI() {
            // Update cart count
            const totalItems = state.cart.reduce((sum, item) => sum + item.quantity, 0);
            elements.cartCount.textContent = totalItems;
            
            // Update cart items
            if (state.cart.length === 0) {
                elements.cartItems.innerHTML = '<div class="empty-cart"><i class="fas fa-shopping-cart"></i><p>Your cart is empty</p></div>';
                elements.cartTotal.textContent = 'R 0.00';
                document.getElementById('checkoutBtn').disabled = true;
            } else {
                elements.cartItems.innerHTML = state.cart.map(item => `
                    <div class="cart-item">
                        <div class="cart-item-image">
                            ${getItemIcon(item.category)}
                        </div>
                        <div class="cart-item-details">
                            <h4>${item.name}</h4>
                            <div>R ${item.price.toFixed(2)}</div>
                            <div class="cart-item-controls">
                                <button class="quantity-btn" onclick="updateCartQuantity(${item.id}, -1)">-</button>
                                <span class="quantity">${item.quantity}</span>
                                <button class="quantity-btn" onclick="updateCartQuantity(${item.id}, 1)">+</button>
                                <button class="remove-item" onclick="removeFromCart(${item.id})">
                                    <i class="fas fa-trash"></i>
                                </button>
                            </div>
                        </div>
                    </div>
                `).join('');
                
                const total = state.cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
                elements.cartTotal.textContent = `R ${total.toFixed(2)}`;
                document.getElementById('checkoutBtn').disabled = false;
            }
        }

        function getItemIcon(category) {
            switch(category) {
                case 'ebook': return '📖';
                case 'coaching': return '🎯';
                case 'workshop': return '👥';
                default: return '📦';
            }
        }

        function toggleCart() {
            elements.cartSidebar.classList.toggle('active');
        }

        // Wishlist Functions
        function toggleWishlistItem(productId) {
            if (!state.user) {
                openAuthModal();
                showNotification('Please log in to manage your wishlist', 'warning');
                return;
            }
            
            const existingIndex = state.wishlist.findIndex(item => item.id === productId);
            
            if (existingIndex !== -1) {
                state.wishlist.splice(existingIndex, 1);
                showNotification('Item removed from wishlist', 'success');
            } else {
                const product = state.products.find(p => p.id === productId);
                if (product) {
                    state.wishlist.push(product);
                    showNotification('Item added to wishlist', 'success');
                }
            }
            
            updateWishlistUI();
        }

        function updateWishlistUI() {
            // Update wishlist count
            elements.wishlistCount.textContent = state.wishlist.length;
            
            // Update wishlist items
            if (state.wishlist.length === 0) {
                elements.wishlistItems.innerHTML = '<div class="empty-wishlist"><i class="fas fa-heart"></i><p>Your wishlist is empty</p></div>';
            } else {
                elements.wishlistItems.innerHTML = state.wishlist.map(item => `
                    <div class="wishlist-item">
                        <div class="wishlist-item-image">
                            ${item.image}
                        </div>
                        <div class="wishlist-item-details">
                            <h4>${item.name}</h4>
                            <div>R ${item.price.toFixed(2)}</div>
                            <div style="margin-top: 0.5rem;">
                                <button class="btn btn-primary" style="padding: 0.25rem 0.5rem; font-size: 0.8rem;" 
                                        onclick="addToCart('${item.name}', ${item.price}, '${item.category}', ${item.id})">
                                    <i class="fas fa-cart-plus"></i> Add to Cart
                                </button>
                                <button class="btn btn-outline" style="padding: 0.25rem 0.5rem; font-size: 0.8rem; margin-left: 0.5rem;" 
                                        onclick="toggleWishlistItem(${item.id})">
                                    <i class="fas fa-trash"></i> Remove
                                </button>
                            </div>
                        </div>
                    </div>
                `).join('');
            }
        }

        function toggleWishlist() {
            elements.wishlistSidebar.classList.toggle('active');
        }

        // Search Functions
        function handleSearch(e) {
            const query = e.target.value.toLowerCase().trim();
            
            if (query.length < 2) {
                elements.searchResults.style.display = 'none';
                return;
            }
            
            // Search across products, blog posts, and workshops
            const results = [];
            
            // Search products
            state.products.forEach(product => {
                if (product.name.toLowerCase().includes(query) || 
                    product.description.toLowerCase().includes(query)) {
                    results.push({
                        type: 'product',
                        icon: '📦',
                        title: product.name,
                        description: product.description,
                        action: () => {
                            scrollToSection('products');
                            elements.searchInput.value = '';
                            elements.searchResults.style.display = 'none';
                        }
                    });
                }
            });
            
            // Search blog posts
            state.blogPosts.forEach(post => {
                if (post.title.toLowerCase().includes(query) || 
                    post.description.toLowerCase().includes(query)) {
                    results.push({
                        type: 'blog',
                        icon: '📝',
                        title: post.title,
                        description: post.description,
                        action: () => {
                            scrollToSection('blog');
                            elements.searchInput.value = '';
                            elements.searchResults.style.display = 'none';
                        }
                    });
                }
            });
            
            // Search workshops
            state.workshops.forEach(workshop => {
                if (workshop.title.toLowerCase().includes(query) || 
                    workshop.description.toLowerCase().includes(query)) {
                    results.push({
                        type: 'workshop',
                        icon: '👥',
                        title: workshop.title,
                        description: workshop.description,
                        action: () => {
                            scrollToSection('workshops');
                            elements.searchInput.value = '';
                            elements.searchResults.style.display = 'none';
                        }
                    });
                }
            });
            
            // Display results
            if (results.length > 0) {
                elements.searchResults.innerHTML = results.map(result => `
                    <div class="search-result-item" onclick="${result.action}">
                        <div class="search-result-icon">${result.icon}</div>
                        <div>
                            <div style="font-weight: bold;">${result.title}</div>
                            <div style="font-size: 0.9rem; color: #6b7280;">${result.description}</div>
                        </div>
                    </div>
                `).join('');
                elements.searchResults.style.display = 'block';
            } else {
                elements.searchResults.innerHTML = '<div class="search-result-item">No results found</div>';
                elements.searchResults.style.display = 'block';
            }
        }

        // Checkout Functions
        function checkout() {
            if (state.cart.length === 0) {
                showNotification('Your cart is empty', 'warning');
                return;
            }
            
            if (!state.user) {
                openAuthModal();
                showNotification('Please log in to checkout', 'warning');
                return;
            }
            
            // Create order
            const order = {
                id: Date.now(),
                date: new Date().toISOString(),
                customerEmail: state.user.email,
                items: [...state.cart],
                total: state.cart.reduce((sum, item) => sum + (item.price * item.quantity), 0)
            };
            
            state.orders.push(order);
            state.cart = [];
            updateCartUI();
            toggleCart();
            
            showNotification('Order placed successfully!', 'success');
        }

        // Contact Form
        function handleContact(e) {
            e.preventDefault();
            showNotification('Message sent successfully! We will get back to you soon.', 'success');
            document.getElementById('contactForm').reset();
        }

        // Utility Functions
        function scrollToSection(sectionId) {
            document.getElementById(sectionId).scrollIntoView({ behavior: 'smooth' });
        }

        function toggleMenu() {
            elements.navContainer.classList.toggle('active');
        }

        function showNotification(message, type = 'info') {
            // Create notification element
            const notification = document.createElement('div');
            notification.className = `notification notification-${type}`;
            notification.innerHTML = `
                <div style="position: fixed; top: 100px; right: 20px; background: ${type === 'success' ? '#10b981' : type === 'error' ? '#ef4444' : type === 'warning' ? '#f59e0b' : '#3b82f6'}; color: white; padding: 1rem; border-radius: 5px; box-shadow: 0 4px 6px rgba(0,0,0,0.1); z-index: 2000; max-width: 300px;">
                    <div style="display: flex; align-items: center; gap: 0.5rem;">
                        <i class="fas fa-${type === 'success' ? 'check-circle' : type === 'error' ? 'exclamation-circle' : type === 'warning' ? 'exclamation-triangle' : 'info-circle'}"></i>
                        <span>${message}</span>
                    </div>
                </div>
            `;
            
            document.body.appendChild(notification);
            
            // Remove after 3 seconds
            setTimeout(() => {
                notification.remove();
            }, 3000);
        }

        function checkCookieConsent() {
            if (!localStorage.getItem('cookieConsent')) {
                document.getElementById('cookieConsent').style.display = 'block';
            }
        }

        function acceptCookies() {
            localStorage.setItem('cookieConsent', 'true');
            document.getElementById('cookieConsent').style.display = 'none';
        }

        // Social Sharing
        function shareOnFacebook() {
            const url = encodeURIComponent(window.location.href);
            const text = encodeURIComponent('Check out The Definitive Word Ministry - Your Destiny Has Been Written');
            window.open(`https://www.facebook.com/sharer/sharer.php?u=${url}&quote=${text}`, '_blank');
        }

        function shareOnTwitter() {
            const url = encodeURIComponent(window.location.href);
            const text = encodeURIComponent('Check out The Definitive Word Ministry - Your Destiny Has Been Written');
            window.open(`https://twitter.com/intent/tweet?url=${url}&text=${text}`, '_blank');
        }

        function shareOnLinkedIn() {
            const url = encodeURIComponent(window.location.href);
            window.open(`https://www.linkedin.com/sharing/share-offsite/?url=${url}`, '_blank');
        }

        function shareOnWhatsApp() {
            const url = encodeURIComponent(window.location.href);
            const text = encodeURIComponent('Check out The Definitive Word Ministry - Your Destiny Has Been Written');
            window.open(`https://wa.me/?text=${text}%20${url}`, '_blank');
        }

        // Initialize the application when DOM is loaded
        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
