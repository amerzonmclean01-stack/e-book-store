<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Your Destiny Has Been Written</title>
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
            padding: 1rem 0;
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
            padding: 0 2rem;
        }

        .logo h1 {
            font-size: 1.8rem;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .logo p {
            font-size: 0.9rem;
            font-style: italic;
            opacity: 0.9;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
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
        }

        .nav-links a:hover {
            opacity: 0.8;
        }

        .user-actions {
            display: flex;
            gap: 1rem;
            align-items: center;
        }

        .cart-icon {
            position: relative;
            cursor: pointer;
        }

        .cart-count {
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

        .menu-toggle {
            display: none;
            background: none;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(30, 58, 138, 0.9), rgba(220, 38, 38, 0.9)), url('https://images.unsplash.com/photo-1532629345422-7515f3d16bb6?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            color: var(--white);
            text-align: center;
            padding: 8rem 2rem;
            position: relative;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h2 {
            font-size: 3rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            font-style: italic;
        }

        /* Sections */
        section {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 2rem;
        }

        section h2 {
            color: var(--prophetic-blue);
            font-size: 2.5rem;
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

        /* Cart Sidebar */
        .cart-sidebar {
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

        .cart-sidebar.active {
            right: 0;
        }

        .cart-header {
            padding: 1.5rem;
            border-bottom: 1px solid #e5e7eb;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: var(--prophetic-blue);
            color: var(--white);
        }

        .cart-header h3 {
            margin: 0;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .close-cart {
            background: none;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
        }

        .cart-items {
            flex-grow: 1;
            overflow-y: auto;
            padding: 1rem;
        }

        .cart-item {
            display: flex;
            gap: 1rem;
            padding: 1rem 0;
            border-bottom: 1px solid #e5e7eb;
        }

        .cart-item-image {
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

        .cart-item-details {
            flex-grow: 1;
        }

        .cart-item-details h4 {
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

        .cart-footer {
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

        .empty-cart {
            text-align: center;
            padding: 2rem;
            color: #6b7280;
        }

        /* Auth Modal */
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
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 10px;
            max-width: 500px;
            width: 90%;
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

        .auth-tabs {
            display: flex;
            margin-bottom: 1.5rem;
            border-bottom: 1px solid #e5e7eb;
        }

        .auth-tab {
            padding: 0.75rem 1.5rem;
            background: none;
            border: none;
            cursor: pointer;
            font-weight: 600;
            color: var(--dark-gray);
            border-bottom: 3px solid transparent;
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

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--prophetic-blue);
            font-weight: bold;
        }

        .form-group input {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #d1d5db;
            border-radius: 5px;
            font-family: inherit;
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
        }

        /* Admin Panel */
        .admin-panel {
            display: none;
            background: var(--light-gray);
            padding: 2rem;
            border-radius: 10px;
            margin-top: 2rem;
        }

        .admin-panel.active {
            display: block;
        }

        .admin-tabs {
            display: flex;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .admin-tab {
            padding: 0.75rem 1.5rem;
            background: var(--white);
            border: 1px solid #d1d5db;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            color: var(--dark-gray);
        }

        .admin-tab.active {
            background: var(--prophetic-blue);
            color: var(--white);
        }

        .admin-content {
            background: var(--white);
            padding: 1.5rem;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        .admin-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 1rem;
        }

        .admin-table th, .admin-table td {
            padding: 0.75rem;
            text-align: left;
            border-bottom: 1px solid #e5e7eb;
        }

        .admin-table th {
            background: var(--light-gray);
            color: var(--prophetic-blue);
        }

        .action-btn {
            padding: 0.25rem 0.5rem;
            border: none;
            border-radius: 3px;
            cursor: pointer;
            font-size: 0.8rem;
        }

        .edit-btn {
            background: var(--warning);
            color: var(--white);
        }

        .delete-btn {
            background: var(--error);
            color: var(--white);
        }

        /* Footer */
        footer {
            background: var(--prophetic-blue);
            color: var(--white);
            text-align: center;
            padding: 3rem 2rem;
            margin-top: 4rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            text-align: left;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
            font-size: 1.2rem;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 0.5rem;
        }

        .footer-section a {
            color: var(--white);
            text-decoration: none;
            transition: opacity 0.3s;
        }

        .footer-section a:hover {
            opacity: 0.8;
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
            background: var(--prophetic-red);
        }

        .footer-bottom {
            margin-top: 2rem;
            padding-top: 1rem;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        /* Utility Classes */
        .alt-bg {
            background: var(--light-gray);
        }

        .text-center {
            text-align: center;
        }

        .hidden {
            display: none !important;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }

            .nav-links {
                display: none;
                flex-direction: column;
                position: absolute;
                top: 100%;
                left: 0;
                right: 0;
                background: var(--prophetic-blue);
                padding: 1rem;
                gap: 1rem;
            }

            .nav-links.active {
                display: flex;
            }

            .user-actions {
                flex-direction: column;
                gap: 0.5rem;
            }

            .hero h2 {
                font-size: 2rem;
            }

            .cart-sidebar {
                width: 100%;
                right: -100%;
            }

            .footer-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .social-links {
                justify-content: center;
            }
        }
    </style>
</head>
<body>
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
            
            <ul class="nav-links" id="navMenu">
                <li><a href="#home"><i class="fas fa-home"></i> Home</a></li>
                <li><a href="#products"><i class="fas fa-book"></i> Products</a></li>
                <li><a href="#coaching"><i class="fas fa-hands-helping"></i> Coaching</a></li>
                <li><a href="#blog"><i class="fas fa-blog"></i> Blog</a></li>
                <li><a href="#workshops"><i class="fas fa-users"></i> Workshops</a></li>
                <li><a href="#ministry"><i class="fas fa-church"></i> Ministry</a></li>
                <li><a href="#contact"><i class="fas fa-envelope"></i> Contact</a></li>
                
                <div class="user-actions">
                    <div class="cart-icon" onclick="toggleCart()">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count">0</span>
                    </div>
                    
                    <div class="auth-buttons">
                        <button class="btn btn-outline" onclick="openAuthModal()">
                            <i class="fas fa-user"></i> Login
                        </button>
                        <button class="btn btn-primary" onclick="openAuthModal('register')">
                            <i class="fas fa-user-plus"></i> Sign Up
                        </button>
                    </div>
                </div>
            </ul>
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

    <!-- Products Section -->
    <section id="products">
        <h2>Featured Products</h2>
        <p class="text-center" style="max-width: 800px; margin: 0 auto 2rem;">
            Dive deep into prophetic wisdom and biblical teaching with our collection of transformative resources.
        </p>
        
        <div class="products-grid">
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
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; margin-top: 2rem;">
            <article style="background: var(--light-gray); padding: 2rem; border-radius: 10px; border-left: 4px solid var(--prophetic-blue);">
                <h3 style="color: var(--prophetic-blue); margin-bottom: 0.5rem;">Walking in Your Prophetic Purpose</h3>
                <p style="font-size: 0.9rem; color: #6b7280; margin-bottom: 1rem;">November 20, 2025</p>
                <p style="margin-bottom: 1rem;">Discovering how to align your daily life with the prophetic words spoken over you...</p>
                <a href="#" style="color: var(--prophetic-blue); text-decoration: none; font-weight: bold;">
                    Read More <i class="fas fa-arrow-right"></i>
                </a>
            </article>

            <article style="background: var(--light-gray); padding: 2rem; border-radius: 10px; border-left: 4px solid var(--prophetic-blue);">
                <h3 style="color: var(--prophetic-blue); margin-bottom: 0.5rem;">The Power of Declared Destiny</h3>
                <p style="font-size: 0.9rem; color: #6b7280; margin-bottom: 1rem;">November 15, 2025</p>
                <p style="margin-bottom: 1rem;">Understanding how God's written word over your life shapes your future...</p>
                <a href="#" style="color: var(--prophetic-blue); text-decoration: none; font-weight: bold;">
                    Read More <i class="fas fa-arrow-right"></i>
                </a>
            </article>

            <article style="background: var(--light-gray); padding: 2rem; border-radius: 10px; border-left: 4px solid var(--prophetic-blue);">
                <h3 style="color: var(--prophetic-blue); margin-bottom: 0.5rem;">Breaking Through Limitations</h3>
                <p style="font-size: 0.9rem; color: #6b7280; margin-bottom: 1rem;">November 10, 2025</p>
                <p style="margin-bottom: 1rem;">Practical steps to overcome the barriers standing between you and your destiny...</p>
                <a href="#" style="color: var(--prophetic-blue); text-decoration: none; font-weight: bold;">
                    Read More <i class="fas fa-arrow-right"></i>
                </a>
            </article>
        </div>
    </section>

    <!-- Workshops Section -->
    <section id="workshops" class="alt-bg">
        <h2>Upcoming Workshops</h2>
        <div style="display: grid; gap: 2rem; margin-top: 2rem;">
            <div style="background: var(--white); border: 2px solid var(--prophetic-blue); padding: 2rem; border-radius: 10px; display: grid; grid-template-columns: 1fr 2fr; gap: 2rem; align-items: center;">
                <div style="background: var(--prophetic-red); color: var(--white); padding: 2rem; text-align: center; border-radius: 10px;">
                    <div style="font-size: 3rem; font-weight: bold;">15</div>
                    <div style="font-size: 1.2rem;">DEC 2025</div>
                </div>
                <div>
                    <h3 style="color: var(--prophetic-blue); margin-bottom: 1rem;">Prophetic Activation Workshop</h3>
                    <p style="margin-bottom: 1rem;">A powerful one-day intensive designed to activate and strengthen your prophetic gifting. Learn to hear God's voice clearly and minister prophetically with confidence.</p>
                    <p><strong>Location:</strong> Virtual (Zoom)</p>
                    <p><strong>Time:</strong> 9:00 AM - 4:00 PM</p>
                    <p><strong>Cost:</strong> R 499.99</p>
                    <button class="btn btn-primary" onclick="addToCart('Prophetic Activation Workshop', 499.99, 'workshop')">
                        <i class="fas fa-ticket-alt"></i> Register Now
                    </button>
                </div>
            </div>

            <div style="background: var(--white); border: 2px solid var(--prophetic-blue); padding: 2rem; border-radius: 10px; display: grid; grid-template-columns: 1fr 2fr; gap: 2rem; align-items: center;">
                <div style="background: var(--prophetic-red); color: var(--white); padding: 2rem; text-align: center; border-radius: 10px;">
                    <div style="font-size: 3rem; font-weight: bold;">22</div>
                    <div style="font-size: 1.2rem;">JAN 2026</div>
                </div>
                <div>
                    <h3 style="color: var(--prophetic-blue); margin-bottom: 1rem;">Destiny Mapping Masterclass</h3>
                    <p style="margin-bottom: 1rem;">Discover God's blueprint for your life and create a practical roadmap to walk in your divine purpose. Limited to 20 participants for personalized attention.</p>
                    <p><strong>Location:</strong> Cape Town, South Africa</p>
                    <p><strong>Time:</strong> 6:00 PM - 9:00 PM</p>
                    <p><strong>Cost:</strong> R 799.99</p>
                    <button class="btn btn-primary" onclick="addToCart('Destiny Mapping Masterclass', 799.99, 'workshop')">
                        <i class="fas fa-ticket-alt"></i> Register Now
                    </button>
                </div>
            </div>
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
                <div style="margin-bottom: 1.5rem;">
                    <label for="name" style="display: block; margin-bottom: 0.5rem; color: var(--prophetic-blue); font-weight: bold;">Name</label>
                    <input type="text" id="name" name="name" style="width: 100%; padding: 0.8rem; border: 1px solid #d1d5db; border-radius: 5px;" required>
                </div>
                <div style="margin-bottom: 1.5rem;">
                    <label for="email" style="display: block; margin-bottom: 0.5rem; color: var(--prophetic-blue); font-weight: bold;">Email</label>
                    <input type="email" id="email" name="email" style="width: 100%; padding: 0.8rem; border: 1px solid #d1d5db; border-radius: 5px;" required>
                </div>
                <div style="margin-bottom: 1.5rem;">
                    <label for="subject" style="display: block; margin-bottom: 0.5rem; color: var(--prophetic-blue); font-weight: bold;">Subject</label>
                    <select id="subject" name="subject" style="width: 100%; padding: 0.8rem; border: 1px solid #d1d5db; border-radius: 5px;" required>
                        <option value="">Select a topic...</option>
                        <option value="products">Products</option>
                        <option value="coaching">Life Coaching</option>
                        <option value="workshops">Workshops</option>
                        <option value="ministry">Ministry Inquiry</option>
                        <option value="other">Other</option>
                    </select>
                </div>
                <div style="margin-bottom: 1.5rem;">
                    <label for="message" style="display: block; margin-bottom: 0.5rem; color: var(--prophetic-blue); font-weight: bold;">Message</label>
                    <textarea id="message" name="message" style="width: 100%; padding: 0.8rem; border: 1px solid #d1d5db; border-radius: 5px; min-height: 120px;" required></textarea>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">
                    <i class="fas fa-paper-plane"></i> Send Message
                </button>
            </form>
        </div>
    </section>

    <!-- Admin Panel (Hidden by default) -->
    <section id="admin" class="hidden">
        <h2>Admin Panel</h2>
        <div class="admin-panel">
            <div class="admin-tabs">
                <button class="admin-tab active" onclick="switchAdminTab('products')">Products</button>
                <button class="admin-tab" onclick="switchAdminTab('users')">Users</button>
                <button class="admin-tab" onclick="switchAdminTab('orders')">Orders</button>
            </div>
            
            <div class="admin-content">
                <div id="admin-products" class="admin-tab-content active">
                    <h3>Manage Products</h3>
                    <button class="btn btn-primary" onclick="openProductModal()">
                        <i class="fas fa-plus"></i> Add New Product
                    </button>
                    <table class="admin-table">
                        <thead>
                            <tr>
                                <th>Name</th>
                                <th>Price</th>
                                <th>Category</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody id="admin-products-table">
                            <!-- Products will be populated here -->
                        </tbody>
                    </table>
                </div>
                
                <div id="admin-users" class="admin-tab-content">
                    <h3>Manage Users</h3>
                    <table class="admin-table">
                        <thead>
                            <tr>
                                <th>Name</th>
                                <th>Email</th>
                                <th>Role</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody id="admin-users-table">
                            <!-- Users will be populated here -->
                        </tbody>
                    </table>
                </div>
                
                <div id="admin-orders" class="admin-tab-content">
                    <h3>Manage Orders</h3>
                    <table class="admin-table">
                        <thead>
                            <tr>
                                <th>Order ID</th>
                                <th>Customer</th>
                                <th>Amount</th>
                                <th>Status</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody id="admin-orders-table">
                            <!-- Orders will be populated here -->
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>The Definitive Word</h3>
                <p>Your Destiny Has Been Written. We are dedicated to helping you discover and walk in your God-given purpose through prophetic teaching and life coaching.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
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
                    <a href="#" class="forgot-password">Forgot Password?</a>
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
                <div class="form-footer">
                    <button type="submit" class="btn btn-primary">Create Account</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Product Modal (for admin) -->
    <div class="modal" id="productModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 id="productModalTitle">Add New Product</h3>
                <button class="close-modal" onclick="closeProductModal()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <form id="productForm">
                <div class="form-group">
                    <label for="productName">Product Name</label>
                    <input type="text" id="productName" required>
                </div>
                <div class="form-group">
                    <label for="productDescription">Description</label>
                    <textarea id="productDescription" required style="width: 100%; padding: 0.8rem; border: 1px solid #d1d5db; border-radius: 5px; min-height: 100px;"></textarea>
                </div>
                <div class="form-group">
                    <label for="productPrice">Price (ZAR)</label>
                    <input type="number" id="productPrice" step="0.01" required>
                </div>
                <div class="form-group">
                    <label for="productCategory">Category</label>
                    <select id="productCategory" required>
                        <option value="ebook">E-book</option>
                        <option value="workshop">Workshop</option>
                        <option value="coaching">Coaching</option>
                        <option value="other">Other</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="productImage">Image URL</label>
                    <input type="text" id="productImage">
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">Save Product</button>
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
            products: [
                {
                    id: 1,
                    name: "Unveiling Your Destiny",
                    description: "A comprehensive guide to discovering and walking in your God-given purpose.",
                    price: 299.99,
                    category: "ebook",
                    image: "📖"
                },
                {
                    id: 2,
                    name: "Prophetic Insights",
                    description: "Understanding the prophetic voice in the modern church and your personal life.",
                    price: 349.99,
                    category: "ebook",
                    image: "🕊️"
                },
                {
                    id: 3,
                    name: "The Written Word",
                    description: "Exploring the power of God's promises and declarations over your life.",
                    price: 269.99,
                    category: "ebook",
                    image: "✝️"
                },
                {
                    id: 4,
                    name: "Prayer & Fasting Guide",
                    description: "A 21-day guide to deepening your prayer life through biblical fasting.",
                    price: 199.99,
                    category: "ebook",
                    image: "🙏"
                }
            ],
            users: [
                {
                    id: 1,
                    name: "Admin User",
                    email: "admin@definitiveword.org",
                    role: "admin",
                    password: "admin123"
                }
            ],
            orders: []
        };

        // DOM Elements
        const elements = {
            cartSidebar: document.getElementById('cartSidebar'),
            cartItems: document.getElementById('cartItems'),
            cartTotal: document.getElementById('cartTotal'),
            cartCount: document.querySelector('.cart-count'),
            authModal: document.getElementById('authModal'),
            productModal: document.getElementById('productModal'),
            paymentModal: document.getElementById('paymentModal'),
            productsGrid: document.querySelector('.products-grid'),
            adminSection: document.getElementById('admin'),
            checkoutBtn: document.getElementById('checkoutBtn')
        };

        // Initialize the application
        function init() {
            renderProducts();
            updateCartUI();
            checkAuthState();
            
            // Set up event listeners
            document.getElementById('loginForm').addEventListener('submit', handleLogin);
            document.getElementById('registerForm').addEventListener('submit', handleRegister);
            document.getElementById('contactForm').addEventListener('submit', handleContact);
            document.getElementById('productForm').addEventListener('submit', handleProductSubmit);
            
            // Check if user is admin
            if (state.user && state.user.role === 'admin') {
                showAdminPanel();
                renderAdminData();
            }
        }

        // Navigation Functions
        function toggleMenu() {
            document.getElementById('navMenu').classList.toggle('active');
        }

        function scrollToSection(sectionId) {
            document.getElementById(sectionId).scrollIntoView({ behavior: 'smooth' });
            toggleMenu(); // Close mobile menu after clicking
        }

        // Cart Functions
        function toggleCart() {
            elements.cartSidebar.classList.toggle('active');
        }

        function addToCart(name, price, category, id = null) {
            const productId = id || Date.now();
            const existingItem = state.cart.find(item => item.id === productId);
            
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                state.cart.push({
                    id: productId,
                    name,
                    price,
                    category,
                    quantity: 1
                });
            }
            
            updateCartUI();
            showNotification(`${name} added to cart!`, 'success');
            
            // Auto-open cart for non-coaching items
            if (category !== 'coaching') {
                elements.cartSidebar.classList.add('active');
            }
        }

        function removeFromCart(id) {
            state.cart = state.cart.filter(item => item.id !== id);
            updateCartUI();
        }

        function updateCartUI() {
            // Update cart items
            elements.cartItems.innerHTML = '';
            
            if (state.cart.length === 0) {
                elements.cartItems.innerHTML = '<div class="empty-cart">Your cart is empty</div>';
                elements.checkoutBtn.disabled = true;
            } else {
                state.cart.forEach(item => {
                    const cartItem = document.createElement('div');
                    cartItem.className = 'cart-item';
                    cartItem.innerHTML = `
                        <div class="cart-item-image">${getProductIcon(item.category)}</div>
                        <div class="cart-item-details">
                            <h4>${item.name}</h4>
                            <div class="price">R ${item.price.toFixed(2)}</div>
                            <div class="cart-item-controls">
                                <button class="quantity-btn" onclick="updateQuantity(${item.id}, -1)">-</button>
                                <span class="quantity">${item.quantity}</span>
                                <button class="quantity-btn" onclick="updateQuantity(${item.id}, 1)">+</button>
                                <button class="remove-item" onclick="removeFromCart(${item.id})">
                                    <i class="fas fa-trash"></i>
                                </button>
                            </div>
                        </div>
                    `;
                    elements.cartItems.appendChild(cartItem);
                });
                elements.checkoutBtn.disabled = false;
            }
            
            // Update cart total and count
            const total = state.cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const count = state.cart.reduce((sum, item) => sum + item.quantity, 0);
            
            elements.cartTotal.textContent = `R ${total.toFixed(2)}`;
            elements.cartCount.textContent = count;
        }

        function updateQuantity(id, change) {
            const item = state.cart.find(item => item.id === id);
            if (item) {
                item.quantity += change;
                if (item.quantity <= 0) {
                    removeFromCart(id);
                } else {
                    updateCartUI();
                }
            }
        }

        function getProductIcon(category) {
            switch(category) {
                case 'ebook': return '📖';
                case 'workshop': return '🎓';
                case 'coaching': return '🎯';
                default: return '📦';
            }
        }

        // Product Functions
        function renderProducts() {
            elements.productsGrid.innerHTML = '';
            
            state.products.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                productCard.innerHTML = `
                    <div class="product-image">${product.image}</div>
                    <div class="product-content">
                        <h3>${product.name}</h3>
                        <p>${product.description}</p>
                        <div class="product-footer">
                            <div class="price">R ${product.price.toFixed(2)}</div>
                            <button class="btn btn-primary" onclick="addToCart('${product.name}', ${product.price}, '${product.category}', ${product.id})">
                                <i class="fas fa-cart-plus"></i> Add to Cart
                            </button>
                        </div>
                    </div>
                `;
                elements.productsGrid.appendChild(productCard);
            });
        }

        // Auth Functions
        function openAuthModal(tab = 'login') {
            elements.authModal.classList.add('active');
            switchAuthTab(tab);
        }

        function closeAuthModal() {
            elements.authModal.classList.remove('active');
        }

        function switchAuthTab(tab) {
            // Update tabs
            document.querySelectorAll('.auth-tab').forEach(t => t.classList.remove('active'));
            document.querySelectorAll('.auth-form').forEach(f => f.classList.remove('active'));
            
            // Activate selected tab
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

        function handleLogin(e) {
            e.preventDefault();
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;
            
            // Simple authentication (in a real app, this would be server-side)
            const user = state.users.find(u => u.email === email && u.password === password);
            
            if (user) {
                state.user = { ...user };
                localStorage.setItem('user', JSON.stringify(state.user));
                closeAuthModal();
                checkAuthState();
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
                role: 'customer'
            };
            
            state.users.push(newUser);
            state.user = { ...newUser };
            localStorage.setItem('user', JSON.stringify(state.user));
            
            closeAuthModal();
            checkAuthState();
            showNotification('Account created successfully!', 'success');
        }

        function logout() {
            state.user = null;
            localStorage.removeItem('user');
            checkAuthState();
            showNotification('Logged out successfully', 'success');
        }

        function checkAuthState() {
            // Check if user is stored in localStorage
            const storedUser = localStorage.getItem('user');
            if (storedUser) {
                state.user = JSON.parse(storedUser);
            }
            
            // Update UI based on auth state
            const authButtons = document.querySelector('.auth-buttons');
            
            if (state.user) {
                authButtons.innerHTML = `
                    <span style="color: white; margin-right: 1rem;">
                        <i class="fas fa-user"></i> Hello, ${state.user.name}
                    </span>
                    ${state.user.role === 'admin' ? 
                        `<button class="btn btn-outline" onclick="toggleAdminPanel()">
                            <i class="fas fa-cog"></i> Admin
                        </button>` : ''}
                    <button class="btn btn-outline" onclick="logout()">
                        <i class="fas fa-sign-out-alt"></i> Logout
                    </button>
                `;
                
                if (state.user.role === 'admin') {
                    showAdminPanel();
                    renderAdminData();
                }
            } else {
                authButtons.innerHTML = `
                    <button class="btn btn-outline" onclick="openAuthModal()">
                        <i class="fas fa-user"></i> Login
                    </button>
                    <button class="btn btn-primary" onclick="openAuthModal('register')">
                        <i class="fas fa-user-plus"></i> Sign Up
                    </button>
                `;
                elements.adminSection.classList.add('hidden');
            }
        }

        // Admin Functions
        function showAdminPanel() {
            elements.adminSection.classList.remove('hidden');
        }

        function toggleAdminPanel() {
            elements.adminSection.classList.toggle('hidden');
            if (!elements.adminSection.classList.contains('hidden')) {
                scrollToSection('admin');
            }
        }

        function switchAdminTab(tab) {
            // Update tabs
            document.querySelectorAll('.admin-tab').forEach(t => t.classList.remove('active'));
            document.querySelectorAll('.admin-tab-content').forEach(c => c.classList.remove('active'));
            
            // Activate selected tab
            document.getElementById(`admin-${tab}`).classList.add('active');
            document.querySelector(`.admin-tab:nth-child(${tab === 'products' ? 1 : tab === 'users' ? 2 : 3})`).classList.add('active');
        }

        function renderAdminData() {
            // Render products table
            const productsTable = document.getElementById('admin-products-table');
            productsTable.innerHTML = '';
            
            state.products.forEach(product => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>${product.name}</td>
                    <td>R ${product.price.toFixed(2)}</td>
                    <td>${product.category}</td>
                    <td>
                        <button class="action-btn edit-btn" onclick="editProduct(${product.id})">
                            <i class="fas fa-edit"></i> Edit
                        </button>
                        <button class="action-btn delete-btn" onclick="deleteProduct(${product.id})">
                            <i class="fas fa-trash"></i> Delete
                        </button>
                    </td>
                `;
                productsTable.appendChild(row);
            });
            
            // Render users table
            const usersTable = document.getElementById('admin-users-table');
            usersTable.innerHTML = '';
            
            state.users.forEach(user => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>${user.name}</td>
                    <td>${user.email}</td>
                    <td>${user.role}</td>
                    <td>
                        <button class="action-btn edit-btn" onclick="editUser(${user.id})">
                            <i class="fas fa-edit"></i> Edit
                        </button>
                        ${user.role !== 'admin' ? 
                            `<button class="action-btn delete-btn" onclick="deleteUser(${user.id})">
                                <i class="fas fa-trash"></i> Delete
                            </button>` : ''}
                    </td>
                `;
                usersTable.appendChild(row);
            });
            
            // Render orders table
            const ordersTable = document.getElementById('admin-orders-table');
            ordersTable.innerHTML = '';
            
            state.orders.forEach(order => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>#${order.id}</td>
                    <td>${order.customerName}</td>
                    <td>R ${order.total.toFixed(2)}</td>
                    <td>${order.status}</td>
                    <td>
                        <button class="action-btn edit-btn" onclick="viewOrder(${order.id})">
                            <i class="fas fa-eye"></i> View
                        </button>
                    </td>
                `;
                ordersTable.appendChild(row);
            });
        }

        function openProductModal(product = null) {
            elements.productModal.classList.add('active');
            
            if (product) {
                document.getElementById('productModalTitle').textContent = 'Edit Product';
                document.getElementById('productName').value = product.name;
                document.getElementById('productDescription').value = product.description;
                document.getElementById('productPrice').value = product.price;
                document.getElementById('productCategory').value = product.category;
                document.getElementById('productImage').value = product.image || '';
                
                // Store product ID for updating
                document.getElementById('productForm').dataset.productId = product.id;
            } else {
                document.getElementById('productModalTitle').textContent = 'Add New Product';
                document.getElementById('productForm').reset();
                delete document.getElementById('productForm').dataset.productId;
            }
        }

        function closeProductModal() {
            elements.productModal.classList.remove('active');
        }

        function handleProductSubmit(e) {
            e.preventDefault();
            
            const productId = document.getElementById('productForm').dataset.productId;
            const name = document.getElementById('productName').value;
            const description = document.getElementById('productDescription').value;
            const price = parseFloat(document.getElementById('productPrice').value);
            const category = document.getElementById('productCategory').value;
            const image = document.getElementById('productImage').value;
            
            if (productId) {
                // Update existing product
                const index = state.products.findIndex(p => p.id === parseInt(productId));
                if (index !== -1) {
                    state.products[index] = {
                        ...state.products[index],
                        name,
                        description,
                        price,
                        category,
                        image: image || state.products[index].image
                    };
                }
            } else {
                // Add new product
                const newProduct = {
                    id: Date.now(),
                    name,
                    description,
                    price,
                    category,
                    image: image || getProductIcon(category)
                };
                state.products.push(newProduct);
            }
            
            closeProductModal();
            renderProducts();
            renderAdminData();
            showNotification(`Product ${productId ? 'updated' : 'added'} successfully!`, 'success');
        }

        function editProduct(id) {
            const product = state.products.find(p => p.id === id);
            if (product) {
                openProductModal(product);
            }
        }

        function deleteProduct(id) {
            if (confirm('Are you sure you want to delete this product?')) {
                state.products = state.products.filter(p => p.id !== id);
                renderProducts();
                renderAdminData();
                showNotification('Product deleted successfully!', 'success');
            }
        }

        function editUser(id) {
            // In a real app, this would open a user edit form
            alert('User edit functionality would be implemented here');
        }

        function deleteUser(id) {
            if (confirm('Are you sure you want to delete this user?')) {
                state.users = state.users.filter(u => u.id !== id);
                renderAdminData();
                showNotification('User deleted successfully!', 'success');
            }
        }

        function viewOrder(id) {
            // In a real app, this would show order details
            alert('Order details would be shown here');
        }

        // Checkout and Payment Functions
        function checkout() {
            if (!state.user) {
                showNotification('Please log in to complete your purchase', 'error');
                openAuthModal();
                return;
            }
            
            if (state.cart.length === 0) {
                showNotification('Your cart is empty', 'error');
                return;
            }
            
            // Check if cart contains coaching session (free item)
            const hasCoaching = state.cart.some(item => item.category === 'coaching');
            const total = state.cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            
            if (hasCoaching && total === 0) {
                // Handle free coaching session booking
                completeFreeOrder();
            } else {
                // Show payment options for paid items
                showPaymentOptions();
            }
        }

        function showPaymentOptions() {
            elements.paymentModal.classList.add('active');
            
            const total = state.cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            
            elements.paymentContent.innerHTML = `
                <h4>Order Summary</h4>
                <div style="margin: 1rem 0;">
                    ${state.cart.map(item => `
                        <div style="display: flex; justify-content: space-between; margin-bottom: 0.5rem;">
                            <span>${item.name} x${item.quantity}</span>
                            <span>R ${(item.price * item.quantity).toFixed(2)}</span>
                        </div>
                    `).join('')}
                    <hr style="margin: 1rem 0;">
                    <div style="display: flex; justify-content: space-between; font-weight: bold;">
                        <span>Total:</span>
                        <span>R ${total.toFixed(2)}</span>
                    </div>
                </div>
                
                <h4>Select Payment Method</h4>
                <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin: 1rem 0;">
                    <button class="btn btn-primary" onclick="processStripePayment()" style="display: flex; flex-direction: column; align-items: center; padding: 1rem;">
                        <i class="fab fa-cc-stripe" style="font-size: 2rem; margin-bottom: 0.5rem;"></i>
                        <span>Credit/Debit Card</span>
                    </button>
                    <button class="btn btn-outline" onclick="processPayPalPayment()" style="display: flex; flex-direction: column; align-items: center; padding: 1rem; border-color: var(--prophetic-blue); color: var(--prophetic-blue);">
                        <i class="fab fa-paypal" style="font-size: 2rem; margin-bottom: 0.5rem;"></i>
                        <span>PayPal</span>
                    </button>
                </div>
                
                <div style="margin-top: 1rem; text-align: center;">
                    <button class="btn" onclick="closePaymentModal()" style="background: #6b7280; color: white; width: 100%;">
                        Cancel
                    </button>
                </div>
            `;
        }

        function closePaymentModal() {
            elements.paymentModal.classList.remove('active');
        }

        function processStripePayment() {
            // In a real implementation, this would integrate with Stripe
            // For demo purposes, we'll simulate a successful payment
            
            const total = state.cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            
            elements.paymentContent.innerHTML = `
                <div style="text-align: center; padding: 2rem;">
                    <div style="font-size: 3rem; color: var(--prophetic-blue); margin-bottom: 1rem;">
                        <i class="fas fa-credit-card"></i>
                    </div>
                    <h4>Processing Payment...</h4>
                    <p>Please wait while we process your payment</p>
                    <div style="margin: 2rem 0;">
                        <div class="spinner" style="border: 4px solid #f3f3f3; border-top: 4px solid var(--prophetic-blue); border-radius: 50%; width: 40px; height: 40px; animation: spin 2s linear infinite; margin: 0 auto;"></div>
                    </div>
                </div>
            `;
            
            // Simulate payment processing
            setTimeout(() => {
                completePaidOrder();
            }, 2000);
        }

        function processPayPalPayment() {
            // In a real implementation, this would integrate with PayPal
            alert('PayPal integration would be implemented here. For demo purposes, we will complete the order.');
            completePaidOrder();
        }

        function completeFreeOrder() {
            // Create order record
            const order = {
                id: Date.now(),
                customerName: state.user.name,
                customerEmail: state.user.email,
                items: [...state.cart],
                total: 0,
                status: 'completed',
                date: new Date().toISOString()
            };
            
            state.orders.push(order);
            
            // Show success message
            showNotification('Your coaching session has been booked! We will contact you shortly.', 'success');
            
            // Clear cart
            state.cart = [];
            updateCartUI();
            toggleCart();
            
            // Show confirmation
            elements.paymentContent.innerHTML = `
                <div style="text-align: center; padding: 2rem;">
                    <div style="font-size: 4rem; color: var(--success); margin-bottom: 1rem;">
                        <i class="fas fa-check-circle"></i>
                    </div>
                    <h4>Booking Confirmed!</h4>
                    <p>Your free coaching session has been scheduled.</p>
                    <p>We will contact you at <strong>${state.user.email}</strong> to confirm the details.</p>
                    <button class="btn btn-primary" onclick="closePaymentModal()" style="margin-top: 1rem;">
                        Continue Shopping
                    </button>
                </div>
            `;
            
            elements.paymentModal.classList.add('active');
        }

        function completePaidOrder() {
            const total = state.cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            
            // Create order record
            const order = {
                id: Date.now(),
                customerName: state.user.name,
                customerEmail: state.user.email,
                items: [...state.cart],
                total: total,
                status: 'completed',
                date: new Date().toISOString()
            };
            
            state.orders.push(order);
            
            // Show success message
            elements.paymentContent.innerHTML = `
                <div style="text-align: center; padding: 2rem;">
                    <div style="font-size: 4rem; color: var(--success); margin-bottom: 1rem;">
                        <i class="fas fa-check-circle"></i>
                    </div>
                    <h4>Payment Successful!</h4>
                    <p>Thank you for your purchase. Your order has been confirmed.</p>
                    <p>Order ID: <strong>#${order.id}</strong></p>
                    <p>Total: <strong>R ${total.toFixed(2)}</strong></p>
                    <p>A confirmation email has been sent to <strong>${state.user.email}</strong></p>
                    <button class="btn btn-primary" onclick="closePaymentModal()" style="margin-top: 1rem;">
                        Continue Shopping
                    </button>
                </div>
            `;
            
            // Clear cart
            state.cart = [];
            updateCartUI();
            
            // Update admin orders if user is admin
            if (state.user && state.user.role === 'admin') {
                renderAdminData();
            }
        }

        // Contact Form Handler
        function handleContact(e) {
            e.preventDefault();
            const formData = new FormData(e.target);
            const name = formData.get('name');
            const email = formData.get('email');
            const subject = formData.get('subject');
            const message = formData.get('message');
            
            // In a real app, this would send the data to a server
            console.log('Contact form submitted:', { name, email, subject, message });
            
            showNotification('Thank you for your message! We will get back to you soon.', 'success');
            e.target.reset();
        }

        // Utility Functions
        function showNotification(message, type = 'info') {
            // Create notification element
            const notification = document.createElement('div');
            notification.className = `notification ${type}`;
            notification.innerHTML = `
                <div style="display: flex; align-items: center; gap: 0.5rem;">
                    <i class="fas fa-${type === 'success' ? 'check-circle' : type === 'error' ? 'exclamation-circle' : 'info-circle'}"></i>
                    <span>${message}</span>
                </div>
                <button onclick="this.parentElement.remove()" style="background: none; border: none; cursor: pointer;">
                    <i class="fas fa-times"></i>
                </button>
            `;
            
            // Style the notification
            notification.style.cssText = `
                position: fixed;
                top: 100px;
                right: 20px;
                background: ${type === 'success' ? '#10b981' : type === 'error' ? '#ef4444' : '#3b82f6'};
                color: white;
                padding: 1rem 1.5rem;
                border-radius: 5px;
                box-shadow: 0 4px 6px rgba(0,0,0,0.1);
                z-index: 1300;
                display: flex;
                align-items: center;
                justify-content: space-between;
                min-width: 300px;
                max-width: 500px;
                animation: slideIn 0.3s ease;
            `;
            
            document.body.appendChild(notification);
            
            // Auto-remove after 5 seconds
            setTimeout(() => {
                if (notification.parentElement) {
                    notification.remove();
                }
            }, 5000);
        }

        // Add CSS for spinner animation
        const style = document.createElement('style');
        style.textContent = `
            @keyframes spin {
                0% { transform: rotate(0deg); }
                100% { transform: rotate(360deg); }
            }
            @keyframes slideIn {
                from { transform: translateX(100%); opacity: 0; }
                to { transform: translateX(0); opacity: 1; }
            }
        `;
        document.head.appendChild(style);

        // Initialize the application when DOM is loaded
        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
